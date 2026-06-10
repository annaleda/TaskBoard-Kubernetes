[Home](../README.MD) | [Home Volume 1]() | << [Capitolo precedente](04-Kind-e-Primo-Cluster.md) | >> [Capitolo successivo](06-ReplicaSet.md)

---

### Architettura TaskBoard


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

