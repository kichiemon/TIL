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