[Home](../README.md) | [Home Volume 1]() 

---
# Backend FastAPI

## Obiettivo

Creare una semplice API CRUD per i task.

## Struttura

```text
backend/
├── app.py
├── requirements.txt
└── Dockerfile
```

## requirements.txt

```txt
fastapi
uvicorn
```

## app.py

```python
from fastapi import FastAPI

app = FastAPI()

tasks = []

@app.get("/health")
def health():
    return {"status": "ok"}

@app.get("/tasks")
def get_tasks():
    return tasks

@app.post("/tasks")
def create_task(task: dict):
    tasks.append(task)
    return task
```

## Avvio locale

```bash
pip install -r requirements.txt
uvicorn app:app --reload
```
## Dockerfile

```dockerfile
FROM python:3.12-slim

WORKDIR /app

COPY requirements.txt .

RUN pip install --no-cache-dir -r requirements.txt

COPY . .

EXPOSE 8000

CMD ["uvicorn", "app:app", "--host", "0.0.0.0", "--port", "8000"]
```


```md
## Build dell'immagine

Dalla directory `backend`:
```
```bash
docker build -t taskboard-api:v1 .
```

```md
## Esecuzione del container
```
```bash
docker run -p 8000:8000 taskboard-api:v1
```
## Test

```bash
curl localhost:8000/health
```
```bash
Invoke-RestMethod http://localhost:8000/health
```

Risultato:

```json
{"status":"ok"}
```
