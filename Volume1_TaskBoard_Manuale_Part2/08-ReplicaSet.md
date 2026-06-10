# ReplicaSet

## Scopo

Garantire che esista sempre un numero definito di Pod.

```yaml
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: nginx-rs
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx
```

## Test

Elimina un pod e verifica che venga ricreato.
