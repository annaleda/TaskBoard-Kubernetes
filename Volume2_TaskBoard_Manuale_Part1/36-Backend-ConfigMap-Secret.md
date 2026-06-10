# Backend con ConfigMap e Secret

## Deployment completo

```yaml
containers:
- name: backend
  image: taskboard-api:v1

  envFrom:
  - configMapRef:
      name: backend-config

  - secretRef:
      name: postgres-secret
```

## Variabili disponibili

APP_ENV
LOG_LEVEL
POSTGRES_USER
POSTGRES_PASSWORD
```

## Test

```bash
kubectl exec -it <pod> -- env
```
