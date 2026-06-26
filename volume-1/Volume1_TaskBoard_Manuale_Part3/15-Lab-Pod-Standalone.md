# Laboratorio 1 - Pod Standalone

## Obiettivo

Imparare a creare, ispezionare e debuggare Pod senza Deployment.

## Scenario

Creeremo:

- nginx
- busybox
- alpine

## Nginx

```bash
kubectl run nginx --image=nginx
```

Verifica:

```bash
kubectl get pods
kubectl describe pod nginx
kubectl logs nginx
```

## BusyBox

```bash
kubectl run busybox --image=busybox -- sleep 3600
```

Accesso:

```bash
kubectl exec -it busybox -- sh
```

## Esercizio

Verificare:
- hostname
- DNS
- connettività verso internet

## Soluzione

```bash
hostname
nslookup kubernetes.default
wget -qO- https://example.com
```
