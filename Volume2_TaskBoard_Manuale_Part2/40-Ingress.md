# Ingress

## Routing

Frontend:

/

Backend:

/api

## Manifest

```yaml
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: taskboard

spec:
  ingressClassName: nginx

  rules:
  - host: taskboard.local

    http:
      paths:

      - path: /
        pathType: Prefix
        backend:
          service:
            name: frontend
            port:
              number: 80

      - path: /api
        pathType: Prefix
        backend:
          service:
            name: backend
            port:
              number: 80
```
