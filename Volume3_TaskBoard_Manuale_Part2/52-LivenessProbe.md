# Liveness Probe

## Scopo

Verificare che il processo sia ancora sano.

```yaml
livenessProbe:
  httpGet:
    path: /health
    port: 8000
```

## Effetto

Se fallisce:
- Kubernetes riavvia il container

## Diagnosi

```bash
kubectl describe pod
kubectl get events
```
