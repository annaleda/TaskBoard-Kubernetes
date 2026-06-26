[Home](../README.md) | [Home Volume 2]()

---
# NetworkPolicy

## Obiettivo

Limitare la comunicazione tra pod.

## Regola

Frontend -> Backend

Backend -> PostgreSQL

## Manifest

```yaml
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: backend-policy
```

## Test

Verificare che pod non autorizzati vengano bloccati.
