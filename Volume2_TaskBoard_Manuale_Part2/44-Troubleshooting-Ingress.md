[Home](../README.md) | [Home Volume 2]()

---
# Troubleshooting Ingress

## Errori comuni

### 404

Service errato.

### 502

Backend non raggiungibile.

### Nessuna risposta

Controller non installato.

## Diagnosi

```bash
kubectl get ingress
kubectl describe ingress
kubectl get svc
```
