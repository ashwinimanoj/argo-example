# Getting started
Create namespace: 

``` kubectl create namespace argo ```

### Create resource from yaml:

``` kubectl apply -n argo -f https://raw.githubusercontent.com/argoproj/argo/stable/manifests/quick-start-postgres.yaml ```

### Port forward to access namespace:

``` kubectl -n argo port-forward deployment/argo-server 2746:2746 ```

http://localhost:2746

### Download argo cli from: https://github.com/argoproj/argo/releases
-------

#### Sample 
``` argo submit -n argo --watch https://raw.githubusercontent.com/argoproj/argo/master/examples/hello-world.yaml
kubectl create -n argo -f 001_helloworld.yaml
argo list -n argo
argo get -n argo @latest
argo logs -n argo @latest
```

#### Cron Workflow
```
argo cron create -n argo 003_cron.yaml
```