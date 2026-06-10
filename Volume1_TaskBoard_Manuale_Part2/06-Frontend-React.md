# Frontend React

## Obiettivo

Creare una semplice interfaccia per visualizzare e creare task.

## Creazione progetto

```bash
npm create vite@latest frontend -- --template react
cd frontend
npm install
```

## Componente principale

```jsx
import { useEffect, useState } from 'react'

function App() {
  const [tasks, setTasks] = useState([])

  useEffect(() => {
    fetch('/api/tasks')
      .then(r => r.json())
      .then(setTasks)
  }, [])

  return (
    <div>
      <h1>TaskBoard</h1>
      {tasks.map((t,i)=><div key={i}>{t.title}</div>)}
    </div>
  )
}

export default App
```
