# DynamoDBにおけるベストプラクティス

see - https://docs.aws.amazon.com/ja_jp/amazondynamodb/latest/developerguide/bp-general-nosql-design.html


## NoSQL 設計の 2 つの重要な概念。

NoSQL 設計では、RDBMS 設計とは異なる考え方が必要です。RDBMS の場合は、アクセスパターンを考慮せずに正規化されたデータモデルを作成できます。その後、新しい質問とクエリの要件が発生したら、そのデータモデルを拡張することができます。各タイプのデータを独自のテーブルに整理できます。

NoSQL 設計は異なります。

- DynamoDB の場合は対照的に、答えが必要な質問が分かるまで、スキーマの設計を開始しないでください。ビジネス上の問題とアプリケーションのユースケースを理解することが不可欠です。
- DynamoDB アプリケーションではできるだけ少ないテーブルを維持する必要があります。設計が優れたアプリケーションでは、必要なテーブルは 1 つのみです。