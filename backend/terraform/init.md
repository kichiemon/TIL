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


