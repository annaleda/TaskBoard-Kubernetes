# RBAC

## Componenti

- Role
- ClusterRole
- RoleBinding
- ClusterRoleBinding

## Role

```yaml
apiVersion: rbac.authorization.k8s.io/v1
kind: Role
metadata:
  name: configmap-reader

rules:
- apiGroups: [""]
  resources: ["configmaps"]
  verbs: ["get","list"]
```
