# Google Cloud Next 2019 DevDay PM

## BigData, Data Management, AI/ML

### Google BQ
wiki 900億

alan turing
alan rickman

partisioningでやって、clusteringでさらに分ける
* clustering b wiki, title

### BI Engine
Data StudioとBigQueryの間に入って、オンメモリでデータを持ち高速に分析
* 無償
* bigQueryに接続できる
    * 時間とお金がかかる

### Persistent UDFs
Queryに対して、数字を理解させようとしている
`mediun_1`
javascriptライブラリのおかげ
`one hundred 22 point 3`を122.3として解釈してくれる


Stackoverflow
whyが早く回答をもらえる
いろんな変数をどう組み合わせて、早く回答をもらえるかどうかを判断するか
→ML

CREATE MODEL ... LOG(lsjl)

Geo Special ?

### Latest BigQuery
* Clustering
* Visualizing with DataStudio
* Machene L
* GIS
* Persistent functions

## BigQuery ML で始めるレコメンデーション入門
どうやってレコメンドエンジンを作る？

### BigQuery ML
* PlayStore 40%がおすすめアプル
* YouTube 60%がおすすめ動画

* BQからデータを移行せずに機械学習モデル作成
* SQLで作れるので開発速度高い
* 一般的なMLタスクとハイパーパラメータチューニングを自動化

CREATE a REPLACE MODEL
サンフランシスコで発表
* BigQuery ML GA
* matrix factorization alpha
* tesorflowのインポート、深層学習
...

### Matrix Factorization

!. アイテム document
2. 特徴量 context
3. 埋め込み表現 embedding
    * e.g. 過去に見た動画、検索キーワード

レコメンドの一般的なアーキテクチャ
候補生成
→スコアリング
→ランキング
  
*候補生成*
コンテンツベースフィルタリング
* 似たコンテンツ。アイテムの類似性
* +新しいコンテンツに強い。コールドスタートに強い
* -人がベクトルを分類しないといけない
強調フィルタリング
* Aと似ているBが好むコンテンツはこれ。
* ユーザーの類似度の計算
* 行列分解
    * matrix Factorization
    * 道のコンテンツをユーザーに提供するときに利用される
* 新しいアイテムは苦手
* 国とか年齢など副次的な情報を取り入れるのが難しい

### Demo

```
create or replace model models.recommend 
option(model_type='matrix_factorization',
user_col='user_id', item_col='product_id',
rating_col='rating', 12_reg=10
) AS
select product_id, user_id, rating 
FROM total_purchases
```

```
select * from ML.PREDICT(MODEL.models.recommend,
select user_id, product_id from susers, products
)
)
```

https://movielends.org

Google Merchandise Store
* 評価データがない
* ユーザーのインタラクションからデータを作る
    * e.g. この商品を２回見ている

```
```
* 評価をつける仕組みがあれば、結構使え王

### まとめ

## Edge AI TensorFlow Lite
オンデバイス機械学習を簡単に
TensorFlow Lite
クラウドから端末での計算に映る流れ。

### スマホ：Android iOS

#### TensorFlow Lite on GPU
5.5倍の速度向上 (pixel 3) 15ms
推論をサポート

これからはGPUを使う野田ポイント

#### Qualcomm DSPの対応: 13.8倍の速度向上
TensorFlow Liteでサポート

## 組み込みLinux ラズパイ
care OS

Googleが作った Edge TPU
Cloud TPU // 学習用。

Edge TPU 42倍
電力消費がかなり小さい

### マイクロコントローラ
イェs認識

### スパコン

## TensorFlow.js


## TensorFlow Graphics
3Dのモデルに対する認識

## Helpful
ML Fareness
生データを使うとバイアスが入るね
ML Fareness: Fareness Indicator

Google AI Principle

## Bits table

### which storage type?

// NoSQL
Cloud Firestore
Cloud Bigtable

3つの製品について詳しく。
// Cloud Storage

```
// awsにアクセスできる
gsutil ls s3://xxxx/xxx/

// copy to aws
gsutil cp next.txt s3://xxxx/xx


gsutil mb -c multi_regional -l asia gs://xxx

gsutil ls gs://xxxx

// s3からのデータ移行
rsync -d -r s3://xxx/ gs://xxxxx
```
// Cloud SQL

HA 高可用性設定ができる


// Cloud Native Database
App + SDK

Cloud Firestore
* Mode of Cloud Frirestore
    * Datastore Mode
    * Native Mode

firepixel.app
* pixcel単位でアプリケーションになっている

明日のセッション4:00~4:20
## Memo
// Cloud Shell



















