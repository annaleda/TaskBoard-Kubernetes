# Rollback

## Cronologia

```bash
kubectl rollout history deployment/backend
```

## Ripristino

```bash
kubectl rollout undo deployment/backend
```

## Caso d'uso

Versione v2 difettosa.

Ripristino immediato alla versione precedente.
