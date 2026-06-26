[Home](../README.md) | [Home Volume 3]()

---
# RoleBinding

## Obiettivo

Associare un Role a un ServiceAccount.

```yaml
apiVersion: rbac.authorization.k8s.io/v1
kind: RoleBinding
metadata:
  name: backend-binding

subjects:
- kind: ServiceAccount
  name: backend-sa

roleRef:
  kind: Role
  name: configmap-reader
  apiGroup: rbac.authorization.k8s.io
```
