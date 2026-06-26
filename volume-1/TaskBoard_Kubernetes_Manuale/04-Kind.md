# Kind

## Cluster

```bash
kind create cluster --name taskboard
kubectl get nodes
```

## Caricare immagini

```bash
kind load docker-image taskboard-api:v1 --name taskboard
```
