### 1 - What happened when we deployed the StatefulSet? What did you notice about the pods and their volumes?

```
I noticed the 'stateful' volumeclaim is created first then the 'stateful' pod is created
```

### 2 - What happened when we deleted a pod from the statefulset?

```
After changing the label there is no change to the pod. after deleting a pod, it is rebuilt with the new label 

[jboone3@WFIL134 4 - stateful_set]$ kubectl get pods --show-labels --watch
NAME               READY   STATUS    RESTARTS   AGE    LABELS
stateful-nginx-0   1/1     Running   0          178m   app_name=sts-nginx,controller-revision-hash=stateful-nginx-7b75d9db74,statefulset.kubernetes.io/pod-name=stateful-nginx-0
stateful-nginx-1   1/1     Running   0          178m   app_name=sts-nginx,controller-revision-hash=stateful-nginx-7b75d9db74,statefulset.kubernetes.io/pod-name=stateful-nginx-1
stateful-nginx-2   1/1     Running   0          5s     app_name=sts-nginx,author=jboone3,controller-revision-hash=stateful-nginx-557b58b989,statefulset.kubernetes.io/pod-name=stateful-nginx-2

```

### 10 - What does OnDelete do??

```
The StatefulSet controller will not automatically update Pods when a modification is made to the StatefulSet's. Instead the update occurs when the pod(s) is rebuilt or next built
```

### 11 - What is another updateStrategy and what does it do?

```
There are two valid update strategies, RollingUpdate and OnDelete. The RollingUpdate update strategy will update all Pods in a StatefulSet, in reverse ordinal order, while respecting the StatefulSet guarantees.
```
