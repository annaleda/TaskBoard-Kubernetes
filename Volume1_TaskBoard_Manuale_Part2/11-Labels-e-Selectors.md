# Labels e Selectors

## Labels

```yaml
labels:
  app: backend
  env: dev
```

## Selectors

```yaml
selector:
  app: backend
```

## Test

```bash
kubectl get pods -l app=backend
```
