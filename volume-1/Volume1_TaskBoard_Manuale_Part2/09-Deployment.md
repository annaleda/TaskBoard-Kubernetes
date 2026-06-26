# Deployment

Il Deployment gestisce ReplicaSet e aggiornamenti.

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: backend
spec:
  replicas: 2
  selector:
    matchLabels:
      app: backend
  template:
    metadata:
      labels:
        app: backend
    spec:
      containers:
      - name: backend
        image: taskboard-api:v1
```

## Scale

```bash
kubectl scale deployment backend --replicas=5
```

## Rollout

```bash
kubectl rollout status deployment backend
```
