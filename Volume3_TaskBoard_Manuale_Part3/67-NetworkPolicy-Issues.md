[Home](../README.md) | [Home Volume 3]()

---
# NetworkPolicy Issues

## Sintomi

Connessioni bloccate.

## Diagnosi

```bash
kubectl get networkpolicy
kubectl describe networkpolicy
```

## Strategia

Verificare:

- namespace
- labels
- ingress rules
- egress rules
