# Docker Compose Completo

[🏠 Home](../README.md) | [📚 Volume 1](./00-SOMMARIO.md) | [<< Dockerfile Frontend](./05-Dockerfile-Frontend.md) | [Kind >>](./07-Kind-e-Primo-Cluster.md)

---

## Obiettivo

In questo capitolo eseguiamo l'intero progetto TaskBoard in locale con Docker Compose.

Avremo:

- backend FastAPI
- frontend React servito da NGINX
- rete Docker condivisa
- build automatica delle immagini

In questa fase PostgreSQL può essere aggiunto successivamente nel Volume 2.

---

## Architettura locale

```text
Browser
   |
localhost:3000
   |
Frontend container
   |
localhost:8000
   |
Backend container
```

---

## Posizione del file

Il file `docker-compose.yaml` deve stare nella root del progetto:

```text
Taskboard/
├── backend/
│   ├── app.py
│   ├── requirements.txt
│   └── Dockerfile
├── frontend/
│   ├── src/
│   ├── package.json
│   └── Dockerfile
└── docker-compose.yaml
```

---

## docker-compose.yaml

Creare il file:

```text
docker-compose.yaml
```

Contenuto:

```yaml
services:

  backend:
    build:
      context: ./backend
    image: taskboard-api:v1
    container_name: taskboard-backend
    ports:
      - "8000:8000"

  frontend:
    build:
      context: ./frontend
    image: taskboard-fe:v1
    container_name: taskboard-frontend
    ports:
      - "3000:80"
    depends_on:
      - backend
```

---

## Avvio dello stack

Dalla root del progetto:

```powershell
docker compose up --build
```

Oppure in background:

```powershell
docker compose up --build -d
```

---

## Verifica container

```powershell
docker compose ps
```

Output atteso:

```text
taskboard-backend    running
taskboard-frontend   running
```

---

## Test backend

PowerShell:

```powershell
irm http://localhost:8000/health
```

Output atteso:

```json
{
  "status": "ok"
}
```

In browser:

```text
http://localhost:8000/docs
```

---

## Test frontend

Aprire:

```text
http://localhost:3000
```

Dovresti vedere la pagina TaskBoard.

---

## Logs

Tutti i log:

```powershell
docker compose logs
```

Solo backend:

```powershell
docker compose logs backend
```

Solo frontend:

```powershell
docker compose logs frontend
```

---

## Entrare nei container

Backend:

```powershell
docker compose exec backend sh
```

Frontend:

```powershell
docker compose exec frontend sh
```

---

## Stop dello stack

```powershell
docker compose down
```

Se vuoi rimuovere anche immagini e volumi non usati:

```powershell
docker system prune
```

Attenzione: `docker system prune` rimuove risorse Docker inutilizzate.

---

## Nota importante sul collegamento frontend/backend

In sviluppo locale il frontend può chiamare:

```text
http://localhost:8000
```

Ma quando frontend e backend saranno dentro Kubernetes, `localhost` non indicherà più il backend.

In Kubernetes useremo:

```text
backend.taskboard.svc.cluster.local
```

oppure, con Ingress:

```text
/api
```

Questa distinzione è fondamentale.

---

## Versione con PostgreSQL, preparatoria al Volume 2

Nel Volume 2 aggiungeremo PostgreSQL.

Una prima bozza sarà:

```yaml
services:

  postgres:
    image: postgres:16
    container_name: taskboard-postgres
    environment:
      POSTGRES_DB: taskboard
      POSTGRES_USER: app
      POSTGRES_PASSWORD: app
    ports:
      - "5432:5432"
    volumes:
      - postgres-data:/var/lib/postgresql/data

volumes:
  postgres-data:
```

Per ora ci concentriamo su frontend e backend.

---

## Troubleshooting

### Porta 8000 già occupata

Verificare chi usa la porta:

```powershell
netstat -ano | findstr :8000
```

Soluzione temporanea:

```yaml
ports:
  - "8001:8000"
```

---

### Porta 3000 già occupata

Cambiare mapping:

```yaml
ports:
  - "3001:80"
```

Poi aprire:

```text
http://localhost:3001
```

---

### Frontend non raggiunge backend

Verificare che il backend risponda:

```powershell
irm http://localhost:8000/health
```

Se il backend funziona ma il frontend no, controllare:

- variabile `VITE_API_URL`
- errori nella console browser
- CORS nel backend

---

## Checklist

- [ ] docker-compose.yaml creato nella root
- [ ] backend buildato
- [ ] frontend buildato
- [ ] backend raggiungibile su localhost:8000
- [ ] frontend raggiungibile su localhost:3000
- [ ] log verificati
- [ ] stack fermato con docker compose down

---

[<< Dockerfile Frontend](./05-Dockerfile-Frontend.md) | [📚 Volume 1](./00-SOMMARIO.md) | [Kind >>](./07-Kind-e-Primo-Cluster.md)
