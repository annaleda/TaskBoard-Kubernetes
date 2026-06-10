# Ingress NGINX su Kind

## Obiettivo

Installare un Ingress Controller nel cluster Kind.

## Installazione

```bash
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/kind/deploy.yaml
```

## Verifica

```bash
kubectl get pods -n ingress-nginx
```

Attendere che il controller sia Running.

## Troubleshooting

```bash
kubectl describe pod -n ingress-nginx
kubectl get events -A
```
