[Home](../README.md) | [Home Volume 1]()

---
# Pod

## Cos'è un Pod

Il Pod è la più piccola unità deployabile in Kubernetes.

## Creazione rapida

```bash
kubectl run nginx --image=nginx
```

## Verifica

```bash
kubectl get pods
```

## Descrizione

```bash
kubectl describe pod nginx
```

## Logs

```bash
kubectl logs nginx
```

## Exec

```bash
kubectl exec -it nginx -- sh
```

## Manifest YAML

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: nginx
spec:
  containers:
  - name: nginx
    image: nginx
```

## Applicazione

```bash
kubectl apply -f pod.yaml
```

## Laboratorio

1. Creare un pod nginx.
2. Creare un pod alpine.
3. Entrare nel pod alpine.
4. Verificare DNS e connettività.

## Errori comuni

### ImagePullBackOff

Immagine inesistente.

### CrashLoopBackOff

Processo principale termina immediatamente.
