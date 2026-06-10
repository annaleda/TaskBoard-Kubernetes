# TaskBoard - Parte 1

## Obiettivo

Deployare il backend FastAPI in Kubernetes.

## Namespace

```bash
kubectl create ns taskboard
```

## Deployment

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: backend
  namespace: taskboard

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
        imagePullPolicy: IfNotPresent

        ports:
        - containerPort: 8000
```

## Service

```yaml
apiVersion: v1
kind: Service
metadata:
  name: backend
  namespace: taskboard

spec:
  selector:
    app: backend

  ports:
  - port: 80
    targetPort: 8000
```

## Verifica

```bash
kubectl get pods -n taskboard
kubectl get svc -n taskboard

kubectl port-forward svc/backend 8080:80 -n taskboard
```

Browser:

```text
http://localhost:8080/health
```

## Risultato atteso

```json
{
  "status":"ok"
}
```
