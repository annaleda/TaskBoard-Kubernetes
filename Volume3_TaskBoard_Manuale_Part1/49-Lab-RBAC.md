# Laboratorio RBAC

## Scenario

Consentire al backend di leggere ConfigMap.

## Passi

1. ServiceAccount
2. Role
3. RoleBinding
4. Test accesso

## Verifica

```bash
kubectl auth can-i get configmaps   --as=system:serviceaccount:default:backend-sa
```
