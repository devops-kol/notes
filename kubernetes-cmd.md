### Deployment
- list of ReplicaSet(список репликасет)
```
kubectl get rs
```
- rollout(откат к предыдущей версии репликасет)
```
kubectl rollout undo deployment my-deployment --to-revision=0
```
- update(обновление)
```
kubectl edit deployment my-deployment
```
