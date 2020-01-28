# Cheatsheet

## Kuberenetes
- Copy Files from a pod to your machine: `kubectl cp {{namespace}}/{{podname}}:path/to/directory /local/path``
  - ex `kubectl cp mongo-0:/dump /local/dump`
- Copy file to pod: `kubectl cp /local/path namespace/podname:path/to/directory`
  - ex `kubectl cp /local/dump mongo-0:/dump`
- Get all deployed contaienrs by repository
  - ex 
  ```
  kubectl get pods -o jsonpath="{..image}" |tr -s '[[:space:]]' '\n' |sort |uniq -c|grep -E -i -w "icgcargo|overture"
  ```

## Docker


