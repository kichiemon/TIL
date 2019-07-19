# 決裁システムでAkkaClusterを使ってみた

TISの人

QR決裁の決裁

Lerna?
→高可用、高スループットを実現するためのソフトウェアスタック

Event Sourcing + CQRS
- Akka Persistence
- Akka Persistence Query
Akka Cluster Sharding

Omotenashi Platform Project

CRUD→Lernaに移行

ES+CQRS
→結果生合成
　→最新の状態をどう取得するか、→AkkaPersistenceが解決策となる

*Akka Persistence* のなかにStateを持っているので、そこから最新の情報を種とっくすることができる  
識別子と状態を保つActorをEntityと呼ぶ

Entityは状態を保つので取扱注意
あるIDのEntityが存在していいのは1箇所だけ。複数箇所にあると生合成が崩れてしまう

→いかにコマンドサイドをスケールさせるのか？？
→Akka Cluster Shardingが解決する


Akka Cluster Shardingはロードバランシングする
* 複数のサーバーにEntityを分散しつつも、IDの一意性は保証してくれる

-----

どこの機能で使う？？？かを議論した
* 決裁に直接関連する機能にだけ適用することにした

CRUDなので、システムにどういう状態があるか、を探す活動を行なった
* 状態の更新をしているのはどこか、という視点
* 外から見える状態は何があるのだろう？== Query

→4つの状態を発見
* QR生成時
* 決裁の進捗確認
* 決裁の完了
* 

Query
* 決裁の進捗通知

2つの状態を発見、Entityとして定義
* QR code State
* Payment transaction state

決裁の進捗→transation actorの状態
履歴一覧は複数のtransactionactorの状態を集約

Entityをstate machineとして設計
* QR unused ←→ used


状態を更新するEventは何だろう？？
TokenActor
* to use started
* expired

TransactionActor
* token read
* payment started
* payment failed
* ...

このイベントをstate machineに当てはめていく

Query sideまで10secondくらいのタイムラグがある
→pub sub notificationという機能を有効にして遅延を短縮できた
→pollingではなく、publishする。ただし、Entityをまたがるイベントの順序が保証されない

split brain
ネットワーク障害などでIDが同じEntityが複数生まれてしまって、..


akka cluster shardingの自動フェイルオーバーo
* split brain resolver
* clusterのnode数が増えるほどダウンタイムが増えていく


データマイグレーション
RDBMS→コマンドサイドのデータを作成した

最初から完璧なリアクティブシステムを達成する必要はない

















