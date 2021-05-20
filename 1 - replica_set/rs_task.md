## Task 1 - 

### 1 - Enter command for scaling the replica set

```
kubectl scale --replicas=3 -f manifests/replica_1.yml

```

### 2 - What happened after applying another pod with matching selectors as the ReplicaSet?

```
Nothing happened; I still have 3 pods running. I used kubectl describe pod nginx-pod along with kubectl describe rs nginx-replica and event message showed, "Container image "nginx:stable-alpine" already present on machine"

```
