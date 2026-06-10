[Home](../README.md) | [Home Volume 3]()

---
# QoS e OOMKilled

## QoS

- Guaranteed
- Burstable
- BestEffort

## OOMKilled

Accade quando il container supera il limite memoria.

Verifica:

```bash
kubectl describe pod
```

Evento tipico:

```text
Reason: OOMKilled
```
