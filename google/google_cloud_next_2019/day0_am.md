# Google Cloud Next 2019 DevDay

## Serverless containers with Cloud Run

### What is serveless?
Operation Model
* デプロイしたいものだけを考えればいい。インフラを気にしない。コードに集中できる
* OSも気にしなくていい。セキュリティ更新も全部やってくれる
* 使った分だけ支払う

Programing Model
* Serviceベース
* Event deiven。
* open。汎用的なコードを書くことができる

### Containers
* Any language, library, binaly
* Ecosystemがある

### Google Cloud Run
Bringing serverless to container

* 数秒でデプロイ
* serverlessネイティブ


### Demo
 #1
Code, build & run

* Image選んで、ボタンポチでデプロイ
* これだけでデプロイ・公開できる
* GKEにもデプロイもカンタン

### Serverless container
Cloud Run (fully managed)
* fully serverless
* No cluster to manage
* Play for what you use
Cloud Run on GKE
* GKE cluster実行できる

### Cloud Run: Play per use

* 使った分だけ支払う
* 1インスタンスあたり、最大80人まで同時実行できる
* 従量課金
    * 100ms単位での課金
### UseCase
Public
* website
* mobile backend
* api endpoin
Private
* Microservices


## Session ID: D0-1
## App Engine Standard 2nd generation runtimes

Application Versining
* blue/green
Traffic Splitting

### gVisor
A container sndbox runtime focused 

### DEMO #2
runtimeとかinstance sizeをapp.ymlで設定する

```app.yml
runtime: ruby25
service: ruby
```

## Knative
### What is Knative?
Kubernetes based open source building blocks for serverless

github.com/knative

Traffic Splitting
* カナリアデプロイカンタン


knative
 event sourcing
 でもでは画像をアップロードしたらvision apiに投げて、labelをMLで導出する:wq

## Anthos

### What is Anthos
managed software stack that allows you to:
* build and run
* cloud base appをon premiseで
* legacy app を cloud に migrate

## Istio Service mesh
connectiong, securing, monitioring, managing

Istio enabling a service
* Istio/proxy proxyがトラフィックを管理する
* serviceがそれぞれ通信するのではなく、proxyでコントロール

### Istio on GKE (Beta)
* いずれ自動で入れられる

一貫性が大事 → Anthos

### Anthos
* Config Management
* 理想を描き、逸脱しないように。

*Policy as code*

MarketplaceからAnthosに入れる

### Cloud Run
今後、Cloud Run をGKE on Premでも、いずれ

### Stackdriver

monitioring, loggingなど

完全にAnthosと統合されている

### Migrate for Anthos (Beta)
Cloud 上のVMに移行するのも可能




