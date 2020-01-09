## Switch Role

`~/.aws/config` を下記のように修正する

```
[profile /* スイッチするプロファイル名 */]
role_arn = /* RoleのARN を書く. */
source_profile = /* スイッチ元となるprofileを指定。 ~/.aws/credentials に記載 */
```

