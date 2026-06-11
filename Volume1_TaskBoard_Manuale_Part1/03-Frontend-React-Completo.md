# Frontend React Completo

[ Home](../README.md) | [ Volume 1](./00-SOMMARIO.md) | [<< Backend FastAPI](./02-Backend-FastAPI.md) | [Dockerfile Frontend >>](./05-Dockerfile-Frontend.md)

---

## Obiettivo

Realizzare il frontend della piattaforma TaskBoard.

Alla fine di questo capitolo avremo:

- un'app React funzionante
- integrazione con il backend FastAPI
- visualizzazione task
- creazione task
- preparazione alla containerizzazione Docker

---

## Architettura

```text
Browser
   |
React
   |
FastAPI
```

---

## Creazione del progetto

```bash
npm create vite@latest frontend -- --template react
cd frontend
npm install
npm run dev
```

---

## Variabili ambiente

File `.env`

```env
VITE_API_URL=http://localhost:8000
```

---

## src/App.jsx

```jsx
import { useEffect, useState } from "react";

const API_URL =
  import.meta.env.VITE_API_URL ||
  "http://localhost:8000";

function App() {
  const [tasks, setTasks] = useState([]);
  const [title, setTitle] = useState("");

  async function loadTasks() {
    const response =
      await fetch(`${API_URL}/tasks`);

    const data =
      await response.json();

    setTasks(data);
  }

  async function createTask(event) {
    event.preventDefault();

    await fetch(`${API_URL}/tasks`, {
      method: "POST",
      headers: {
        "Content-Type": "application/json"
      },
      body: JSON.stringify({ title })
    });

    setTitle("");
    loadTasks();
  }

  useEffect(() => {
    loadTasks();
  }, []);

  return (
    <main>
      <h1>TaskBoard</h1>

      <form onSubmit={createTask}>
        <input
          value={title}
          onChange={(e) => setTitle(e.target.value)}
          placeholder="Nuovo task"
        />

        <button type="submit">
          Aggiungi
        </button>
      </form>

      <ul>
        {tasks.map((task, index) => (
          <li key={index}>{task.title}</li>
        ))}
      </ul>
    </main>
  );
}

export default App;
```

---

## Test backend

PowerShell:

```powershell
irm http://localhost:8000/health
```

Output:

```json
{
  "status": "ok"
}
```

---

## Avvio frontend

```bash
npm run dev
```

Aprire:

```text
http://localhost:5173
```

---

## Troubleshooting

### Errore CORS

Configurare CORS nel backend FastAPI.

### Backend non raggiungibile

```powershell
irm http://localhost:8000/health
```

### Porta occupata

```bash
npm run dev -- --port 3000
```

---

## Checklist

- [ ] React installato
- [ ] Vite configurato
- [ ] Backend raggiungibile
- [ ] Lista task caricata
- [ ] Creazione task funzionante

---

[<< Backend FastAPI](./02-Backend-FastAPI.md) | [📚 Volume 1](./00-SOMMARIO.md) | [Dockerfile Frontend >>](./07-Dockerfile-Frontend.md)
