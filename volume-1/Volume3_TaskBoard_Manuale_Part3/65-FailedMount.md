[Home](../README.md) | [Home Volume 3]()

---
# FailedMount

## Sintomi

Pod non avviato.

## Cause

- PVC inesistente
- PVC Pending

## Diagnosi

```bash
kubectl describe pod
kubectl get pvc
```

## Verifica

```bash
kubectl describe pvc
```
