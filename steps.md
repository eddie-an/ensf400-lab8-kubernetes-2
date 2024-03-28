
```shell
$ minikube start
```

```shell
$ minikube addons enable ingress
```

```shell
$ kubectl get pods --all-namespaces -l app.kubernetes.io/name=ingress-nginx
NAMESPACE       NAME                                        READY   STATUS      RESTARTS   AGE
ingress-nginx   ingress-nginx-admission-create-jtxq6        0/1     Completed   0          63s
ingress-nginx   ingress-nginx-admission-patch-j7tcm         0/1     Completed   1          63s
ingress-nginx   ingress-nginx-controller-7c6974c4d8-6vdh6   1/1     Running     0          63s
```

### Create Resources for nginx

```shell
$ kubectl apply -f nginx-svc.yaml
```

```shell
$ kubectl create -f nginx-ingress.yaml
```

```shell
$ kubectl apply -f nginx-configmap.yaml
```

```shell
$ kubectl apply -f nginx-dep.yaml
```

```shell
$ curl -kL http://192.168.49.2/nginx
```

### Create Resources for app 1

```shell
$ kubectl apply -f app-1-svc.yaml
```

```shell
$ kubectl create -f app-1-ingress.yaml
```


```shell
$ kubectl apply -f app-1-dep.yaml
```


### Create Resources for app 2

```shell
$ kubectl apply -f app-2-svc.yaml
```

```shell
$ kubectl create -f app-2-ingress.yaml
```


```shell
$ kubectl apply -f app-2-dep.yaml
```

```shell
$ minikube ip
```