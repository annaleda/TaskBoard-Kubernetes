# ConfigMap Approfondito

## Obiettivo

Separare configurazione e codice.

## Creazione imperativa

```bash
kubectl create configmap backend-config   --from-literal=APP_ENV=dev   --from-literal=LOG_LEVEL=info
```

## Manifest YAML

```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: backend-config
data:
  APP_ENV: dev
  LOG_LEVEL: info
```

## Utilizzo come variabili ambiente

```yaml
envFrom:
- configMapRef:
    name: backend-config
```

## Verifica

```bash
kubectl exec -it <pod> -- env
```

## Troubleshooting

### ConfigMap non trovata

Verificare:

```bash
kubectl get configmap
kubectl describe configmap backend-config
```
