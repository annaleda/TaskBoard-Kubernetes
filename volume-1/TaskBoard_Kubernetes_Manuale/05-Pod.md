# Pod

## Creazione rapida

```bash
kubectl run nginx --image=nginx
```

## YAML

```bash
kubectl run nginx --image=nginx --dry-run=client -o yaml > pod.yaml
```

## Laboratorio

- Pod nginx
- Pod alpine
- Pod busybox

## Troubleshooting

```bash
kubectl describe pod nginx
kubectl logs nginx
```
