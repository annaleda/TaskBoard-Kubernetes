# Namespace

```bash
kubectl create namespace taskboard
```

Applicazione:

```bash
kubectl apply -f deployment.yaml -n taskboard
```

Visualizzazione:

```bash
kubectl get all -n taskboard
```
