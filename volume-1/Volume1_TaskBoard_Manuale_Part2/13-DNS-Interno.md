# DNS Interno

Ogni Service riceve un nome DNS.

## Esempio

Service:

```text
backend
```

DNS:

```text
backend.default.svc.cluster.local
```

## Laboratorio

Creare un pod busybox:

```bash
kubectl run tester --image=busybox -- sleep 3600
```

Entrare:

```bash
kubectl exec -it tester -- sh
```

Verificare:

```bash
nslookup backend
```
