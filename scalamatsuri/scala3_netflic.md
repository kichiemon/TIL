# Scala3

Netflixの人。

open connect
近いところに

Data Drivenな決定。
ABテストをたくさん行なっている

あtらしいUIを試すとき
100万人に対して平行にテストを行なっている

## limited enumeration

```

enum PlayType(desc: String) {
  case A extends PlayType("start a")
  case B extends PlayType("start b")
}
```

## Either union

String | Exception | ...

val movie: Movie | Null = null
movie // duration呼べない


## AnyVal
case class A() extends AnyVal
opaque type
NonEmptyを使う場合に拡張しやすい


## implicit

## Type Class Hack

implicit parameter
→ delegate for Encoder[Movie] = ???
given (Encoder[T], HttpClient) : = ???

## Untyped Equally

## Trait parameter

trait A[F[_](implicit ConcurrentEffect)]{}

## tupple

case 不要になった
Option(1, 2).map((a,b) => ???)

## Cross complication

クロスコンパイル

http://dotty.epfl.ch

https://scastie.scala-lang.org/w6faTgPDRJO48puusnIBhA

https://jobs.netflix.com
























