# Laboratorio 2 - Multi Container Pod

## Obiettivo

Comprendere il modello sidecar.

## Manifest

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: multi-container
spec:
  containers:

  - name: nginx
    image: nginx

  - name: busybox
    image: busybox
    command:
    - sleep
    - "3600"
```

## Applicazione

```bash
kubectl apply -f multi-container.yaml
```

## Accesso

```bash
kubectl exec -it multi-container -c nginx -- sh
kubectl exec -it multi-container -c busybox -- sh
```

## Concetti

- network namespace condiviso
- localhost condiviso
- volumi condivisi
