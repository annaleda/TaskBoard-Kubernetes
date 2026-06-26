[Home](../README.md) | [Home Volume 2]()

---
### PersistentVolumeClaim

## Problema

Se il pod PostgreSQL viene eliminato, i dati spariscono.

## PVC

```yaml
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: postgres-pvc
spec:
  accessModes:
  - ReadWriteOnce
  resources:
    requests:
      storage: 1Gi
```

## Verifica

```bash
kubectl get pvc
```
