[Home](../README.md) | [Home Volume 1]() | << [Capitolo precedente](04-Kind-e-Primo-Cluster.md) | >> [Capitolo successivo](06-ReplicaSet.md)

---
### Docker Fondamenti

## Immagini e Container

Un'immagine è un template immutabile.
Un container è un'istanza in esecuzione.

## Dockerfile Backend

```dockerfile
FROM python:3.12-slim

WORKDIR /app

COPY requirements.txt .

RUN pip install -r requirements.txt

COPY . .

CMD ["uvicorn","app:app","--host","0.0.0.0","--port","8000"]
```

## Build

```bash
docker build -t taskboard-api:v1 .
```

## Run

```bash
docker run -p 8000:8000 taskboard-api:v1
```

## Debug

```bash
docker ps
docker logs <container>
docker exec -it <container> sh
```

## Esercizio

Modifica l'applicazione aggiungendo un endpoint /version.
