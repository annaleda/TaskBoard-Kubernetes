# Dockerfile Frontend React

[ Home](../README.md) | [ Volume 1](./00-SOMMARIO.md) | [<< Frontend React](./03-Frontend-React-Completo.md) | [Docker Compose >>](./06-Docker-Compose-Completo.md)

---

## Obiettivo

In questo capitolo creiamo il Dockerfile del frontend React.

Il frontend viene costruito con Vite e servito tramite NGINX.

Il flusso sarà:

```text
Codice React
   |
npm run build
   |
file statici in dist/
   |
NGINX
   |
container frontend
```

---

## Posizione del file

Il Dockerfile deve stare nella cartella:

```text
Taskboard/
└── frontend/
    ├── src/
    ├── package.json
    ├── vite.config.js
    └── Dockerfile
```

---

## Dockerfile

Creare il file:

```text
frontend/Dockerfile
```

Contenuto:

```dockerfile
FROM node:22-alpine AS build

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

RUN npm run build

FROM nginx:1.27-alpine

COPY --from=build /app/dist /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
```

---

## Spiegazione

### Primo stage: build React

```dockerfile
FROM node:22-alpine AS build
```

Questo stage usa Node.js per installare le dipendenze e compilare il progetto React.

---

```dockerfile
WORKDIR /app
```

Imposta la directory di lavoro dentro il container.

---

```dockerfile
COPY package*.json ./
```

Copia `package.json` e, se presente, `package-lock.json`.

---

```dockerfile
RUN npm install
```

Installa le dipendenze.

---

```dockerfile
COPY . .
```

Copia il resto del codice frontend.

---

```dockerfile
RUN npm run build
```

Genera i file statici nella cartella:

```text
dist/
```

---

### Secondo stage: runtime NGINX

```dockerfile
FROM nginx:1.27-alpine
```

Usa NGINX come web server leggero.

---

```dockerfile
COPY --from=build /app/dist /usr/share/nginx/html
```

Copia i file generati da Vite nella directory servita da NGINX.

---

```dockerfile
EXPOSE 80
```

Documenta che il container espone la porta 80.

---

## Build dell'immagine

Dalla cartella `frontend`:

```powershell
docker build -t taskboard-fe:v1 .
```

Verifica:

```powershell
docker images
```

Output atteso:

```text
REPOSITORY       TAG
taskboard-fe     v1
```

---

## Esecuzione del container

```powershell
docker run -p 3000:80 taskboard-fe:v1
```

Aprire nel browser:

```text
http://localhost:3000
```

---

## Debug

Visualizzare i container:

```powershell
docker ps
```

Visualizzare i log:

```powershell
docker logs <container-id>
```

Entrare nel container:

```powershell
docker exec -it <container-id> sh
```

---

## Nota importante sulle variabili ambiente Vite

Le variabili `VITE_*` vengono lette durante la fase di build.

Questo significa che, se nel frontend hai:

```javascript
import.meta.env.VITE_API_URL
```

il valore viene incorporato quando esegui:

```bash
npm run build
```

Per il laboratorio iniziale va bene.

Più avanti, con Kubernetes e Ingress, useremo un approccio più semplice:

```javascript
fetch('/api/tasks')
```

così sarà l'Ingress a instradare `/api` verso il backend.

---

## Troubleshooting

### La pagina NGINX si apre ma non vedo React

Probabile problema nella build.

Verifica localmente:

```powershell
npm run build
```

---

### Il container parte ma il browser non risponde

Verifica il mapping porte:

```powershell
docker ps
```

Devi vedere qualcosa del tipo:

```text
0.0.0.0:3000->80/tcp
```

---

### Errore durante npm install

Elimina `node_modules` e riprova:

```powershell
Remove-Item -Recurse -Force node_modules
npm install
```

---

## Checklist

- [ ] Dockerfile creato nella cartella frontend
- [ ] Build immagine completata
- [ ] Container avviato
- [ ] Frontend raggiungibile su localhost:3000
- [ ] Log verificati

---

[<< Frontend React](./03-Frontend-React-Completo.md) | [📚 Volume 1](./00-SOMMARIO.md) | [Docker Compose >>](./06-Docker-Compose-Completo.md)
