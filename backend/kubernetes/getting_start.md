# Tutorial

## Commands

`kubectl`


```
$ kubectl config view
$ kubectl get events
$ kubectl get event
$ kubectl get pods
$ kubectl get deployments
$ kubectl get services

# クラスタに参加しているNodeの一覧を取得
$ kubectl get nodes
```

### Create deployment

// --imageでimageを指定
```
$ kubectl create deployment hello-node --image=hello-kubernetes
```

### Run

```
$ kubectl expose deployment hello-node --type=LoadBalancer --port=8080
$ kubectl get services
```

### Clean

```
$ kubectl delete service hello-node
$ kubectl delete deployment hello-node
```

### Dashboard

```
$ kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v1.10.1/src/deploy/recommended/kubernetes-dashboard.yaml
$ kubectl proxy
$ open http://localhost:8001/api/v1/namespaces/kube-system/services/https:kubernetes-dashboard:/proxy/#!/login
```

### install minikube 
```
$ brew cask install minikube
$ minikube start
$ minikube dashboard
$ kubectl create deployment hello-node --image=gcr.io/hello-minikube-zero-install/hello-node
$ kubectl config view
$ kubectl get events
$ kubectl get pods
$ kubectl get deployments
$ kubectl expose deployment hello-node --type=LoadBalancer --port=8080 // --type=LoadBalancerフラグはServiceをクラスタ外部に公開したいことを示しています。
$ minikube service hello-node
```
