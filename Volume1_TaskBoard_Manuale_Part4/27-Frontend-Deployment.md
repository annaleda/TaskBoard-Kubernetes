# Deploy Frontend React

## Deployment

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: frontend

spec:
  replicas: 2

  selector:
    matchLabels:
      app: frontend

  template:
    metadata:
      labels:
        app: frontend

    spec:
      containers:
      - name: frontend
        image: taskboard-fe:v1
        imagePullPolicy: IfNotPresent
        ports:
        - containerPort: 80
```

## Service

```yaml
kind: Service
metadata:
  name: frontend
```

## Verifica

```bash
kubectl get deploy
kubectl get svc
```
