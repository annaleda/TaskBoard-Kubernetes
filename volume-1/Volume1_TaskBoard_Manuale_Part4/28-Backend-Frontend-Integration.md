# Integrazione Frontend e Backend

## Architettura

```text
Frontend
    |
    v
Backend
```

## Comunicazione

Frontend:

```javascript
fetch('/api/tasks')
```

Backend:

```text
backend.taskboard.svc.cluster.local
```

## Test

```bash
kubectl port-forward svc/frontend 3000:80
```
