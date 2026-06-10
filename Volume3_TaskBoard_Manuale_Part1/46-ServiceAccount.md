# ServiceAccount

## Cos'è

Un ServiceAccount rappresenta un'identità per i Pod.

## Creazione

```yaml
apiVersion: v1
kind: ServiceAccount
metadata:
  name: backend-sa
```

## Applicazione

```bash
kubectl apply -f serviceaccount.yaml
```

## Utilizzo

```yaml
spec:
  serviceAccountName: backend-sa
```

## Verifica

```bash
kubectl get sa
```
