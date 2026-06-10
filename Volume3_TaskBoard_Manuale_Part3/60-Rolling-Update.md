# Rolling Update

## Obiettivo

Aggiornare un'applicazione senza downtime.

## Aggiornamento immagine

```bash
kubectl set image deployment/backend   backend=taskboard-api:v2
```

## Monitoraggio

```bash
kubectl rollout status deployment/backend
```

## Verifica

```bash
kubectl get rs
kubectl get pods
```

## Vantaggi

- disponibilità continua
- aggiornamento graduale
