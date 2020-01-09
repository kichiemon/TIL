# Start Terraform

# AWS

## How to setup AWS account

Use aws CLI.

```
$ aws configure --profile appsync-ios-terraformer
AWS Access Key ID [None]: **********************
AWS Secret Access Key [None]: **********************
Default region name [None]: ap-northeast-1
Default output format [None]:
```

`$home/.aws/credentials` に設定が入るようになる

Terraformからは、

```
provider "aws" {
  profile = "my-profile-name"
}
```

で利用する。

## BackendをS3に設定する

- 事前にS3にバケットを作っておく必要があるので、手で作る
- tfstateの保存場所をS3に設定する
```
terraform {
  backend "s3" {
    bucket  = "my-tfstate-store-name-at-s3" # backet name
    key     = "hogehoge/terraform.tfstate"
    profile = "my-profile-name"
  }
}
```
- terraform initする

