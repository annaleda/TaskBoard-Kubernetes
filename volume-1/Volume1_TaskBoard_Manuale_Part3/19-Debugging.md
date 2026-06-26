# Debugging Kubernetes

## Comandi fondamentali

```bash
kubectl get all
kubectl get events
kubectl describe pod
kubectl logs
kubectl exec
```

## Metodo sistematico

1. Stato Pod
2. Eventi
3. Logs
4. Container
5. Networking

## Esempio

```bash
kubectl get pods
kubectl describe pod backend
kubectl logs backend
```
