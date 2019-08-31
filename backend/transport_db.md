# DBの移行

## 外部MySQLからAuroraDBへ

[参考](https://docs.aws.amazon.com/ja_jp/AmazonRDS/latest/UserGuide/MySQL.Procedural.Importing.NonRDSRepl.html)

> また、区切り文字付きテキスト形式を使用することによってもたらされるメリットに対して、mysqldump のパフォーマンスの重み付けをする必要があります。区切り文字付きテキスト形式を使用したバックアップでは、ダンプされる各テーブルについてタブ区切りテキストファイルを作成されます。LOAD DATA LOCAL INFILE コマンドを使用してこれらのファイルを並行してロードできるため、データベースのインポートに必要な時間を短縮できます。mysqldump 形式を選択してデータをロードする方法の詳細については、MySQL のドキュメントの「バックアップでの mysqldump の使用」を参照してください。


```
mysqldump -u <local_user> \
    --databases <database_name> \
    --single-transaction \
    --compress \
    --order-by-primary  \
    -p<local_password> | mysql -u <RDS_user> \
        --port=<port_number> \
        --host=<host_name> \
        -p<RDS_password>
```





