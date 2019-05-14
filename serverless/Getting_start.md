# serverless framework tutorial




## Create a new service

```
# Create a new Serverless Service/Project
$ serverless create --template aws-nodejs --path my-service
# Change into the newly created directory
$ cd my-service
```


## Deploy

変更を反映させる時

```
$ serverless deploy -v
```

Deploy the Function

functionを素早く反映したい時

```
$ serverless deploy function -f hello
```

## Account

AWSアカウントの指定ができる

1. `~/.aws/credentials`
2. serverless.ymlに利用するアカウントを記載。profileに記載
```
service: new-service
provider:
  name: aws
  runtime: nodejs6.10
  stage: dev
  profile: devProfile
```
3. あるいは、コマンド実行時に指定。`serverless deploy --aws-profile devProfile`
4. 環境ごとにアカウントを変えるには
```
service: new-service
provider:
  name: aws
  runtime: nodejs6.10
  stage: ${opt:stage, self:custom.defaultStage}
  profile: ${self:custom.profiles.${self:provider.stage}}
custom:
  defaultStage: dev
  profiles:
    dev: devProfile
    prod: prodProfile
```

## Invoke Local


Localで試すには

```
$ serverless invoke local --function functionName
```

https://serverless.com/framework/docs/providers/aws/cli-reference/invoke-local/#aws---invoke-local

## Install service

サービスをインストールする

```
$ serverless install --url https://github.com/some/service
```

e.g. 

```
$ serverless install --url https://github.com/pmuens/serverless-crud
```
