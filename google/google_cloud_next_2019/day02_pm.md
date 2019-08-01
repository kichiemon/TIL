## App Engine

// VPC 接続 (beta) 
年内にGA目指す

App Engine と Cloud Runとの相互運用

あらゆるApp Engine
+ Dockerコンテナイメージ

時期焦燥の最適化が諸悪の根源
* 必要のないものも入れてしまいがち

スピードが命
作りたいプロトタイプを短期間で。

品質に妥協しない
プロダクトを批判しても人を非難しない

モノリスからスタートしましょう。
純粋なマイクロサービスを最初から構築しようとすると混乱に陥ります
// モノリスからスタートして、マイクロサービスに移行する、移行しやすいモノリス、移行しにくいモノリスとは？

組織や技術的な課題に直面した時にマイクロサービスへの分割を選択肢に入れよう

サービスは技術的、組織的に独立している

* 最低一人で運用
* 独立してデプロイ可能
* バージョン管理された安定したAPIで通信

成長し、新チームへ分割していくと、戦略へ過大な投資をしてしまう。
何を、なぜ、行うのか、みんなで一致させてください
// リーダーシップ
// 最終的なゴールを同じものに

Q. App EngineのフレキシブルEnvとCloudRunの使い分けはどうすればいい？
Cloud Runの方がinstance追加したりしやすい


## Cloud Code とコンテナツールで、Kubernetesを使った開発を徹底効率化
Google Cloud Japan 岩成さん

// コンテナ or Kubernetes ?
コンテナ != Kubernetes

CGPにおける実行環境の選択肢
* GAE // ソースコードベース
* Cloud Run // コンテナベース
* GKE // コンテナベース

開発ワークフロー
Local Dev →　CI → CD

**Local開発を対象としている！**
Local開発をどういう風に効率化するのか

### Kubernetesを使ったローカル開発効率化

Code → build →　push ↓
yaml → patch　→　　　deploy →　connect → very app

→　開発者はコードにフォーカスしたい。しかしやることがたくさん....

難しいところ
* コードの変更のたびに繰り返し作業が発生 painful dev cycle
* コンテキストスイッチによって生産性が低下 context switch
* Kubernetes、関連ツールを覚えるのが困難。学習コスト high learning cost

What is Cloud Code for IDEs?

Google Cloud Codeは統合されたツールセットで、ツールチェーン...
開発者が**コードを書き、価値を高めることにフォーカス**

Cloud Codeは二つの選択肢
* VSCode
* IntelliJ

特徴。IDEのなかで基本実現できる
* k8sの開発サイクル。自動化
* デバッグ
* クラスタ管理
* テンプレートと編集支援
* エコシステムとの統合
* Google Cloud Platformとの統合

Scaffoldが裏で動いている
* k8sの継続的デプロイメントをサポートするツール

### Demo

VSCode
* extension でcloud code → install
* kubernetesのリソースを観れる
* てmプレートを使って新しいアプリを作れる

deploy
* continuous deploy // コードを変更すると勝手にデプロイ
* deploy


## Cloud Run ~ Knative サーバーレス
篠原さん

What is Serverless?

GCPのサーバーレスはフルスタック
* 全部の領域を対象としている


GCPのサーバーレスコンピュート
* funcitons
* app engine
* Cloud run

なぜCloud Runが必要だったのか？
これまでは、、、
* 使える言語やライブラリが限定的

Knative
* Kubernetes上にサーバーレス環境を実現する

Knative?
* OSS
* コンテナをサーバーレスライクに使える
* Kubernetesクラスターのハードウェアリソースが使える(GPU/TPU)

Cloud Run ?
Knativeをベースにした新しいサーバーレス

特徴
* 高速なデプロイ
* サーバーレス
* ポータビリティ

二つのサービス
* Cloud Run
    * 使った分だけ課金
* Cloud Run on GKE
    * 使った分＋GKEの料金

// Twitter
cloud run % cloud run on gke















































