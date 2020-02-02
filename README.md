# Cheatsheet

## Kuberenetes
- Copy Files from a pod to your machine: 
```
kubectl cp {{namespace}}/{{podname}}:path/to/directory /local/path
kubectl cp mongo-0:/dump /local/dump
```
- Copy file to pod: 
```
kubectl cp /local/path namespace/podname:path/to/directory
kubectl cp /local/dump mongo-0:/dump
```
- Get all deployed contaienrs by repository
```
kubectl get pods -o jsonpath="{..image}" |tr -s '[[:space:]]' '\n' |sort |uniq -c|grep -E -i -w "icgcargo|overture"
```

## Docker


## linux
- kill all process by grep expression, example
```
$kill -9 $(ps ax | grep node | awk {'print$1'})
```
