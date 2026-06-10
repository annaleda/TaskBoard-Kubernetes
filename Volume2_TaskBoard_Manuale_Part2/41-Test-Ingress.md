[Home](../README.md) | [Home Volume 2]()

---
# Test Ingress

## Hosts

Aggiungere:

```text
127.0.0.1 taskboard.local
```

## Verifica

```bash
curl http://taskboard.local/api/health
```

Risultato atteso:

```json
{"status":"ok"}
```
