[Home](../README.md) | [Home Volume 2]()

---
# Laboratorio NetworkPolicy

## Scenario

Creare:

- frontend
- backend
- postgres

Applicare policy.

## Verifica

Pod tester:

```bash
kubectl run tester --image=busybox -- sleep 3600
```

Provare connessioni autorizzate e non.
