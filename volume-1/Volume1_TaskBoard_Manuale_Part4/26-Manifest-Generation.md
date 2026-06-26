# Generazione Manifest

## Pod

```bash
kubectl run nginx   --image=nginx   --dry-run=client   -o yaml
```

## Deployment

```bash
kubectl create deployment nginx   --image=nginx   --dry-run=client   -o yaml
```

## Service

```bash
kubectl expose deployment nginx   --port=80   --target-port=80   --dry-run=client   -o yaml
```
