# ImagePullBackOff

## Manifest errato

```yaml
image: nginx:not-existing
```

## Diagnosi

```bash
kubectl describe pod
```

Output tipico:

```text
Failed to pull image
```

## Soluzione

Utilizzare un tag esistente.
