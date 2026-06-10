[Home](../README.md) | [Home Volume 3]()

---
# Readiness Probe

## Scopo

Indica quando un container è pronto a ricevere traffico.

```yaml
readinessProbe:
  httpGet:
    path: /health
    port: 8000
  initialDelaySeconds: 5
  periodSeconds: 10
```

## Effetto

Se la probe fallisce:
- il Pod resta Running
- il Service non invia traffico

## Test

Creare un endpoint inesistente e osservare il comportamento.
