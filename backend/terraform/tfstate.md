# tfstateを管理する


## S3で共有

tfstateの保存場所をS3に設定する方法

```
terraform {
  backend "s3" {
    bucket  = "my-tfstate-store-name-at-s3"
    key     = "hogehoge/terraform.tfstate"
    profile = "my-profile-name"
  }
}
```
