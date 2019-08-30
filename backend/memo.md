awsのs3とデータを同期する

`aws s3 [localfilePath] s3://[bucket_name] --exact-timestamps`

--exact-timestamps : 変更時間も見て差分があれば同期。これをつけないと、サイズが一緒なら同期されない

















