# Deployment e ReplicaSet

## Deployment

```yaml
apiVersion: apps/v1
kind: Deployment
spec:
  replicas: 3
```

## Scale

```bash
kubectl scale deployment nginx --replicas=5
```

## Rollout

```bash
kubectl rollout history deployment nginx
kubectl rollout undo deployment nginx
```
