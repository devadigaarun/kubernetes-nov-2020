## KUBECTL

- `kubectl` is a kubernete client / cli that can connect with on-premise or cloud based kubernetes

- `kubectl` is a REST client that communicates with `API-SERVER` (Installed on MASTER-NODE) on secure HTTPS port (443 or 6443).

- `kubectl` uses a YAML configuration stored at `%homepath%\.kube\config`

## KUBECTL Command reference

`kubectl [Verb] [TypeOfObject] [ObjectName]`

`kubectl [Verb] -f [PathToYAMLfile]`

Object Type | short name | full name
------------|------------|-----------
Pod | po | pod / pods
ReplicaSet | rs | replicaset / replicasets
Deployment | deploy | deployment / deployments
Service | svc | service / services 
Service Endpoints | ep | <NA>
Storage Class | sc | storageclass / storageclasses
Stateful Set | sts | statefulset / statefulsets
config maps | cm | configmap / configmaps
Secret | <NA> | secret / secrets
Persisted Volumes | pv | persistedvolume 
Persisted Volume Claims | pvc | persistedvolumeclaims

Verbs | Description |Examples
------|-------------|-------------
get | Get short details of objects of given type  |kubectl get po
get | Get short details of single object of given type | kubectl get po pod1
describe | Describe in details an objects of given type | kubectl describe po
describe | Describe in details a single object of given type | kubectl describe po pod1
apply | Read the YAML/JSON file and push the changes (Create/Update) to API Server | kubectl apply -f pod1.yml
delete | Delete the objects from given YAML/JSON file | kubectl delete -f pod1.yml
delete | Delete the objects from cmd-line | kubectl delete po pod1



