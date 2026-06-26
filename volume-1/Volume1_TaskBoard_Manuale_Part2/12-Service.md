# Service

## ClusterIP

```yaml
apiVersion: v1
kind: Service
metadata:
  name: backend
spec:
  selector:
    app: backend
  ports:
  - port: 80
    targetPort: 8000
```

## Test

```bash
kubectl port-forward svc/backend 8080:80
```
