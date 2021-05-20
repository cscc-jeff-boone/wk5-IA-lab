### 1 - What is notice about the output replicaset of your command?
### *hint* - ``` kubectcl get rs --show-labels```

```
Notice that the name of the ReplicaSet is always formatted as [DEPLOYMENT-NAME]-[RANDOM-STRING]. The random string is randomly generated and uses the pod-template-hash as a seed.

# Sourced from https://kubernetes.io/docs/concepts/workloads/controllers/deployment/

Also found same result for answer using kubectl get rs -o wide. in my case the name was nginx-deployment-68bd8845dd
```

### 2 - What did you notice about the labels of the pods after updating?
### *hint* - ``` kubectcl get rs --show-labels```

```
I noticed two things:
1) I got a new unique deployment/replica
2) the labels are auto-sorted (alphabetically) and not by list order in manifest
```

### 3 - What is the command for rolling back a deployment to revision 1?

```
kubectl rollout undo deployment.v1.apps/nginx-deployment
or
kubectl rollout undo deployment.v1.apps/nginx-deployment --to-revision=1

```
