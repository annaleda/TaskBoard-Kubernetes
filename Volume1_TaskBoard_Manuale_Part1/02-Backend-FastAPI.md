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

## Test

```bash
curl localhost:8000/health
```

Risultato:

```json
{"status":"ok"}
```
