# Imperative vs Declarative

## Imperative

```bash
kubectl run nginx --image=nginx
```

## Declarative

```bash
kubectl apply -f pod.yaml
```

## CKAD

Saper usare entrambi gli approcci.

## Generare YAML

```bash
kubectl run nginx   --image=nginx   --dry-run=client   -o yaml > pod.yaml
```
