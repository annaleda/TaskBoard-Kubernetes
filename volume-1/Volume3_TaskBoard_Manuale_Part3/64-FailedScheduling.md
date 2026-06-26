[Home](../README.md) | [Home Volume 3]()

---
# FailedScheduling

## Sintomi

Pod Pending.

## Cause comuni

- CPU insufficiente
- memoria insufficiente
- node selector errato

## Diagnosi

```bash
kubectl describe pod
kubectl get events
```

## Evento tipico

```text
0/1 nodes available
```
