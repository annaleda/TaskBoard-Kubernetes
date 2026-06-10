[Home](../README.md) | [Home Volume 3]()

---
# CronJobs

## Scopo

Eseguire task pianificati.

## Manifest

```yaml
apiVersion: batch/v1
kind: CronJob
metadata:
  name: cleanup

spec:
  schedule: "*/5 * * * *"

  jobTemplate:
    spec:
      template:
        spec:
          restartPolicy: Never
          containers:
          - name: cleanup
            image: busybox
            command:
            - sh
            - -c
            - date
```

## Verifica

```bash
kubectl get cronjobs
kubectl get jobs
```
