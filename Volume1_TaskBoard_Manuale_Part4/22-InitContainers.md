# Init Containers

## Cos'è un Init Container

Un Init Container viene eseguito prima dei container principali.

## Caso d'uso

Attendere che il database sia disponibile.

```yaml
initContainers:
- name: wait-db
  image: busybox
  command:
  - sh
  - -c
  - until nslookup postgres; do sleep 2; done
```

## Vantaggi

- inizializzazione
- migrazioni
- controlli preliminari
