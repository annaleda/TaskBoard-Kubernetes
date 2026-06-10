# Kind

## Creazione Cluster

kind-config.yaml

```yaml
kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4
nodes:
- role: control-plane
```

Creazione:

```bash
kind create cluster --name taskboard --config kind-config.yaml
```

Verifica:

```bash
kubectl cluster-info
kubectl get nodes
```

## Caricare immagini

```bash
kind load docker-image taskboard-api:v1 --name taskboard
```

## Troubleshooting

### Nessun nodo disponibile

```bash
docker ps
kind get clusters
```
