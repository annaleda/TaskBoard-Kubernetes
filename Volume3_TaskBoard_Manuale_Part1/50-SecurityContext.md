# SecurityContext

## Obiettivo

Eseguire container con privilegi minimi.

```yaml
securityContext:
  runAsNonRoot: true
  runAsUser: 1000
  allowPrivilegeEscalation: false
```

## Best Practice

- Non usare root
- Ridurre privilegi
- Limitare filesystem
