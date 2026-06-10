# CrashLoopBackOff

## Descrizione

Il container parte e termina continuamente.

## Manifest rotto

```yaml
containers:
- name: test
  image: busybox
  command:
  - exit
```

## Diagnosi

```bash
kubectl describe pod
kubectl logs
kubectl get events
```

## Soluzione

Usare un processo persistente:

```yaml
command:
- sleep
- "3600"
```
