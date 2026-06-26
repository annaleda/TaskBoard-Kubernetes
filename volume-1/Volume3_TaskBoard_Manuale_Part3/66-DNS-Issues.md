[Home](../README.md) | [Home Volume 3]()

---
# DNS Issues

## Test

Pod debug:

```bash
kubectl run dns-test   --image=busybox   -- sleep 3600
```

Verifica:

```bash
kubectl exec -it dns-test -- nslookup backend
```

## Diagnosi

```bash
kubectl get svc
kubectl get endpoints
```
