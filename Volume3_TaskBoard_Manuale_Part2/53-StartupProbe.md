# Startup Probe

## Quando usarla

Applicazioni lente ad avviarsi.

```yaml
startupProbe:
  httpGet:
    path: /health
    port: 8000
  failureThreshold: 30
  periodSeconds: 10
```

Evita riavvii prematuri durante il bootstrap.
