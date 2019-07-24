# Spotify Scio
データ処理について

#flatmap data infrastructure

## use case 色々
* 聞いている人がどこにいるのか、どの地域で人気があるか、とか。

## scalability スケーラビリティに課題
* volume of data
* number of datasets
* number of data-engineers / data-scientists


いろんな人を想定してやっていかないといけない

* スケジューリング
* オーケストレーション
* テスと
* 予算n
* ストレージ

GDPR、トラブル、インシデント、などなど、対応しなければならない
* 間違ったデータ・数字から間違った判断を下されることを避けないと。

データプロセッシングは難しい、そして高い
DATA PROCESSING is HARD & EXPENSIVE

いまは、確実に動く、段階にいる
目指すのは効率と簡単

Scio

Spotify x Scio

## about scio
https://github.com/spotify/scio

* ドキュメントが豊富
* 予想性、実効性能、生産性、が高い。 // エンジニアの時間を無駄にしたくない
* 型安全


* Data engineering
* Scala Cemter advisory board member
* open sourdce :)
https://github.com/spotify

## Efficiency : serialization
Scio 0.7.0 では、性的なCoderが追加
BigQueryのクライアントを再設計、IOをりふぁくたりんぐ

Coders in 0.7
* 型安全。
* Runtimeではなくコンパイル時に自動導出


Results
* Anonymisation job
    匿名化のジョブ
    * 個人情報を暗号化
* 匿名化ジョブの時間短縮か


## Efficiency : join
Soft Merge Bucket join
SMB
* Shardingする
* 圧縮がよりできるので、storageコスト削減できる

Scioの0.8でApatcheBeamが入る
* BeamSQL
  * 型安全が失われている
  * typed sqlを導入した
  * sql -> tsql




