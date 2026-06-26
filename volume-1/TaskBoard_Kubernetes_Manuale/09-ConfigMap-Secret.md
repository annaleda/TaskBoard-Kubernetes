# ConfigMap e Secret

## ConfigMap

```bash
kubectl create configmap app-config --from-literal=ENV=dev
```

## Secret

```bash
kubectl create secret generic db-secret --from-literal=password=test
```

## Laboratorio

Montare ConfigMap come env var.
