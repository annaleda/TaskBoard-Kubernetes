# Command e Args

## Override del comando

```yaml
containers:
- name: busybox
  image: busybox
  command:
  - sleep
  args:
  - "3600"
```

## Laboratorio

Creare un pod che stampa:

```text
Hello Kubernetes
```

e termina.
