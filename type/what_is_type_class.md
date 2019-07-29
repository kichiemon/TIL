# Cats

## Cats???

* 似た性質を持つ型のグループ
    * Cats事前定義されている
* 型のグループの加入審査
* 新たな構文
* データ型

基本的な型のグループを紹介して、

# 畳み込み

## 足し算

* `List(0, 1, 2).foldLeft(0)(_ + _)`
* foldLeft[Int]は単純
List[Either[Error, Int]]は？
List[Future[Either[Error, Int]]]は？


Right(0):Either[Error, Int]

* 型のネストが多くなると、そのぶん、構造の分解が必要
* foldLeftに渡す関数に本来いらない処理を含める必要がある...

畳み込みを分割

## 共通の性質を基にして型のグループが定義されている


e.g. Semigroup, Monoid


Semigroup[T] は、不変
* Tは不変

## 空の値
* 型ごとに決めることができそう

Monoid
* wつの値を１つにまとめられる & 空の値を定義できる
* すべてのMonoidはSemigroupである

## 畳み込み方
* catsが提供するFoldable
* 畳み込みができる
* foldLeft, foldRight

## foldLeftとFoldable.foldどっちがいい？
* foldLeft
    * 初期値や足し合わせが柔軟
        * 本来モデル化すべきロジックが紛れ込む危険
*

Foldableの落とし穴
* なぜobject methodにするのか？
    * 同名のメソッドが既に定義されているから
`:` context bound


# 計算の合成

* e.g. Future

直列
* forで合成

並列
* forの外でやらないといけない

前の計算結果に依存するような合成に便利
並列に対してはあまり向いていない

Monad
* 直列した計算を表す型グループ
* flatMap, pure, tailRecM
* flatMapはMonadの合成
/// scalaはstack over flowになるが、catsはstack safe。tailRecM

Applicative
* 依存関係がない、並列した計算を表す
* ap, pure
* 全てのMonadはApplicativeでもある
    * e.g. Either, List, Option, Future
```
Applicative[Future].map2(
repp1.resolve(1),
repo2.resolve(2)
).mapN(_ + _)
```

ApplicativeとMonadの違い
* FutureのApplicativeからEitherのApplicativeをあわせて
    * Future[Eigher[T]]
* Monadは積み上げられない
→ Monad Transformer
* Monadを積み上げたいときに使う
    * e.g. type EitherTFuture[T] = EitherT[Future, Error, T]

// これだとまだだめ。taxingもEitherTFutureにしないといけない
```
Applicative[EitherTFuture].map2(
repo1.resolve(1).flatMap(taxing),
repo2.resolve(1).flatMap(taxing)
)(_ + _)
```
→ Kleisli
* Monadを生成する関数のラッパー
* Kleisli[F, A, B]はA => F[B] のラッパー
* runメソッドでA => F[B]へアクセス可能
* FがMonadなら、KleisliもMonadになる

e.g.
```
type EitherTFuture = EitherT[Future, Error, Int]
def taxing(value: Int): Future[Int] = ???
val taxingEF = Kleisli(taxing).mapF(f => EitherT(f.map(_.asRight[Error]))).run(0)

Applicative[EitherTFuture].map2(
repo1.resolve(1).flatMap(taxingEF.run),
repo2.resolve(1).flatMap(taxingEF.run)
)(_ + _)
```
* 2段までにしたほうがいい。3段になると死ぬ


## たあt見込みへ再び
Foldable.foldMapM
```
List(1, 2, 3).foldMapM(
goodETRepo.resolveById _ andThen (_.map(_.price))
)
```
* repositoryからの取得が直列実行される



Future.sequenceをFutureいがいでもつかいたい

```.scala
val secenced: Either[Error, List[Price]] = 
list.foldRight(List.empty()){
(e, acc) =>
  for {
  value <- e
  valueList <- acc
  } yield value :: valueList
  
}
```
Applicativeの匂い


Traverse
* TraverseはApplicativeである
* Traverse.secquence
```.scala
val secenced: Either[Error, List[Price]] = 
list.foldRight(List.empty()){
(e, acc) =>
  for {
  value <- e
  valueList <- acc
  } yield value :: valueList
  
}
```

