# serverless framework tutorial

## Install tools

### Install AWS CLI
```
$ brew install awscli
```

### Install ServerlessFramework

* yarnl

```
$ yarn init -y
```

```
$ npm install serverless
```

## Getting Start

### Set up
```
# install aws cli
$ brew install awscli

# install yarn & serverless 
$ brew install yarn
$ yarn init -y
$ yarn add serverless --dev

# 必要に応じて
$ yarn add serverless-offline --dev
$ yarn add serverless-dynamodb-local --dev

# setup aws account
# Serverless用のIAMユーザを発行
# 必要な権限はこちら https://gist.github.com/ServerlessBot/7618156b8671840a539f405dea2704c8
$ yarn serverless config credentials --provider aws --key 1234 --secret 5678 --profile serverless-agent
```

### Create a new service


Templateはこちら
- https://serverless.com/framework/docs/providers/aws/cli-reference/create#available-templates

```
# Create a new Serverless Service/Project
$ serverless create --template aws-nodejs --path my-service
# or $ serverless create -t aws-nodejs -p my-service

# Change into the newly created directory
$ cd my-service
```

### Run Local


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

## serverlessをglobalに入れない

```
npm install serverless --save-dev
yarn add serverless --dev
```

### localに入れたserverlessを実行するには

To execute the locally installed Serverless executable you have to reference the binary out of the node modules directory.

Example:

node ./node_modules/serverless/bin/serverless deploy
yarn serverless deploy
eval (yarn bin)/sls plugin install -n serverless-offline


## Organization

https://serverless.com/framework/docs/providers/aws/guide/services#organization
