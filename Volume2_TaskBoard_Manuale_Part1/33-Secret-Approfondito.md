# Secret Approfondito

## Creazione

```bash
kubectl create secret generic postgres-secret   --from-literal=POSTGRES_USER=app   --from-literal=POSTGRES_PASSWORD=supersecret
```

## YAML

```yaml
apiVersion: v1
kind: Secret
metadata:
  name: postgres-secret
type: Opaque
stringData:
  POSTGRES_USER: app
  POSTGRES_PASSWORD: supersecret
```

## Utilizzo

```yaml
envFrom:
- secretRef:
    name: postgres-secret
```

## Best Practice

- Mai committare password reali
- Separare Secret e Deployment
- Limitare accessi RBAC
