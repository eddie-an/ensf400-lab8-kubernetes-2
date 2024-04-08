
```shell
$ minikube start
```

```shell
$ minikube addons enable ingress
```

Confirm that ingress is enabled

```shell
$ kubectl get pods --all-namespaces -l app.kubernetes.io/name=ingress-nginx
NAMESPACE       NAME                                        READY   STATUS      RESTARTS   AGE
ingress-nginx   ingress-nginx-admission-create-jtxq6        0/1     Completed   0          63s
ingress-nginx   ingress-nginx-admission-patch-j7tcm         0/1     Completed   1          63s
ingress-nginx   ingress-nginx-controller-7c6974c4d8-6vdh6   1/1     Running     0          63s
```

### Create deployments, services, and configmap
Go to `assignment3` directory

Run

```shell
$ kubectl apply -f "*.yaml"
```

### Create ingress

Change directory to `assignment3/ingress`

```shell
$ cd ingress
```

```shell
$ kubectl create -f "app-1-ingress.yaml"
```

```shell
$ kubectl create -f "app-2-ingress.yaml"
```


### Running app
```shell
$ curl -kL http://$(minikube ip)/
```

---

#### Troubleshooting tips

```shell
$ kubectl logs -l app.kubernetes.io/name=ingress-nginx -n ingress-nginx
```