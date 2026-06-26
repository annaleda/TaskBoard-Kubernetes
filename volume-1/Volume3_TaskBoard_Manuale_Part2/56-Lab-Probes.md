[Home](../README.md) | [Home Volume 3]()

---
# Laboratorio Probes

## Obiettivo

Configurare:

- Readiness
- Liveness
- Startup

## Test

1. Endpoint corretto.
2. Endpoint errato.
3. Verificare restart e stato Ready.

Comandi:

```bash
kubectl get pods -w
kubectl describe pod
```
