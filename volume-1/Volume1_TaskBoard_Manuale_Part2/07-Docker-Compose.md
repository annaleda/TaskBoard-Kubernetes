# Docker Compose

## Obiettivo

Eseguire Frontend, Backend e PostgreSQL localmente.

```yaml
services:
  backend:
    build: ./backend
    ports:
      - "8000:8000"

  frontend:
    build: ./frontend
    ports:
      - "3000:80"

  postgres:
    image: postgres:16
    environment:
      POSTGRES_DB: taskboard
      POSTGRES_USER: app
      POSTGRES_PASSWORD: app
```

## Avvio

```bash
docker compose up -d
```
