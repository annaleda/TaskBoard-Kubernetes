# Architettura TaskBoard

## Obiettivo

Costruire una piattaforma full-stack composta da:

- Frontend React
- Backend FastAPI
- PostgreSQL

## Architettura finale

```text
Browser
   |
Ingress (Volume 2)
   |
Frontend Service
   |
Frontend Pod
   |
Backend Service
   |
Backend Pod
   |
PostgreSQL
```

## Perché questo progetto

Durante il percorso toccherai:
- Container
- Networking
- Storage
- Security
- Troubleshooting

## Repository

```text
taskboard/
├── backend/
├── frontend/
├── docker-compose.yaml
└── k8s/
```

## Esercizio

Disegna la stessa architettura indicando quali componenti saranno container e quali risorse Kubernetes.
