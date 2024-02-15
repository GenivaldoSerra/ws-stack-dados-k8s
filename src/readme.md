# ws-stack-dados-k8s


### kubernetes cluster
```shell
```

### argocd [gitops]
```shell
```

### minio [deepstorage]
```shell
kubectl apply -f app-manifests/deepstorage/minio-operator.yaml
kubectl apply -f app-manifests/deepstorage/minio-tenant.yaml
```

### hive metastore [metastore]
```shell
kubectl apply -f app-manifests/metastore/hive-metastore.yaml
```

### trino [warehouse]
```shell
htpasswd -Bbn orion newpassword > trn-pwd-file && \
htpasswd -Bbn dev newpassword >> trn-pwd-file && \
htpasswd -Bbn luanmoreno newpassword >> trn-pwd-file

kubectl create secret generic trino-password-file --from-file=trn-pwd-file --namespace warehouse
kubectl apply -f app-manifests/warehouse/trino.yaml
```