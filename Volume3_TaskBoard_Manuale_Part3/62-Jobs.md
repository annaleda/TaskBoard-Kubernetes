# Jobs

## Scopo

Eseguire task una sola volta.

## Manifest

```yaml
apiVersion: batch/v1
kind: Job
metadata:
  name: migration-job
spec:
  template:
    spec:
      restartPolicy: Never
      containers:
      - name: migration
        image: busybox
        command:
        - sh
        - -c
        - echo migration completed
```

## Verifica

```bash
kubectl get jobs
kubectl logs job/migration-job
```
