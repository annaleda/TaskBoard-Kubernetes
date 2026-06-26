[Home](../../README.md) | [Home Volume 1]()

---

# Architettura TaskBoard

L'obiettivo del progetto è realizzare una piattaforma full-stack containerizzata e orchestrata con Kubernetes composta da:

- Frontend React
- Backend FastAPI
- Database PostgreSQL
- API Gateway (NGINX)
- Kubernetes

---

# Architettura finale

```text
                    Browser
                       │
                NodePort (30080)
                       │
               API Gateway (NGINX)
                       │
          ┌────────────┴────────────┐
          │                         │
          │                         │
     Frontend Service          Backend Service
        (ClusterIP)              (ClusterIP)
          │                         │
     Frontend Pod             Backend Pod
                                     │
                              PostgreSQL Service
                                 (ClusterIP)
                                     │
                               PostgreSQL Pod
                                     │
                              Persistent Volume
```

---

## Ruolo dei componenti

| Componente | Funzione |
|------------|----------|
| **NodePort** | Espone il progetto all'esterno del cluster |
| **API Gateway** | Punto di ingresso unico e routing delle richieste |
| **Frontend** | Interfaccia utente React |
| **Backend** | API REST sviluppate con FastAPI |
| **PostgreSQL** | Persistenza dei dati |
| **Persistent Volume** | Conservazione dei dati del database |

---

## Perché questa architettura

Durante il progetto vengono affrontati i principali aspetti di Kubernetes:

- Containerizzazione con Docker
- Orchestrazione dei Pod
- Networking (Service, ClusterIP e NodePort)
- API Gateway
- Storage persistente
- ConfigMap e Secret
- Sicurezza applicativa
- Troubleshooting e Debug

---

## Struttura del repository

```text
taskboard/
│
├── frontend/
│   ├── src/
│   ├── public/
│   └── Dockerfile
│
├── backend/
│   ├── app/
│   ├── requirements.txt
│   └── Dockerfile
│
├── k8s/
│   ├── frontend/
│   ├── backend/
│   ├── database/
│   ├── gateway/
│   ├── configmaps/
│   ├── secrets/
│   └── storage/
│
├── docker-compose.yaml
└── README.md
```
