# Docker

## Dockerfile Backend

```dockerfile
FROM python:3.12-slim
WORKDIR /app
COPY . .
RUN pip install -r requirements.txt
CMD ["uvicorn","app:app","--host","0.0.0.0"]
```

## Comandi

```bash
docker build -t taskboard-api:v1 .
docker run -p 8080:8080 taskboard-api:v1
docker logs <id>
docker exec -it <id> sh
```

## Esercizi
1. Costruire immagine.
2. Eseguire container.
3. Analizzare log.
