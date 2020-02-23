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
a more detailed and better way to get it containers by pod:
```
kubectl get pods -o=jsonpath='{range .items[*]}{"\n"}{.metadata.name}{"|"}{range .spec.containers[*]}{.image}{", "}{end}{end}'| sort | grep -E -i -w "icgcargo|overture"

output example:
clinical-argo-qa-97cf5cfdd-l54m9|icgcargo/clinical:1.0.2, 
```
## Docker


## linux
- kill all process by grep expression, example
```
$kill -9 $(ps ax | grep node | awk {'print$1'})
```
- list disk usage `df`
- check top disk usage in subdirectories `du -h | sort -nr | head -10`
- recalculate the disk (if you increase the size as in aws ebs) `resize2fs /dev/xvda1`
