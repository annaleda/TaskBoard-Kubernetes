# Services e DNS

## ClusterIP

```yaml
kind: Service
```

## Test DNS

```bash
kubectl exec -it tester -- nslookup backend
```

## Port Forward

```bash
kubectl port-forward svc/backend 8080:8080
```
