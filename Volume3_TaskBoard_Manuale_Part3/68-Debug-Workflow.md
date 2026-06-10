# Workflow di Debug

## Metodo consigliato

1. Verificare stato risorsa

```bash
kubectl get all
```

2. Analizzare eventi

```bash
kubectl get events --sort-by=.metadata.creationTimestamp
```

3. Analizzare pod

```bash
kubectl describe pod
```

4. Analizzare log

```bash
kubectl logs
```

5. Entrare nel container

```bash
kubectl exec -it
```
