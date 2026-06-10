# Environment Variables

## Variabili statiche

```yaml
env:
- name: APP_ENV
  value: dev
```

## Test

```bash
kubectl exec -it pod -- env
```

## Laboratorio

Passare:

DB_HOST
DB_PORT
APP_ENV
