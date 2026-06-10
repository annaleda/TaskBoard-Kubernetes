# Laboratorio PostgreSQL Persistente

## Obiettivo

Verificare che i dati sopravvivano al riavvio del pod.

## Passi

1. Creare PVC
2. Creare Deployment PostgreSQL
3. Collegare volume
4. Inserire dati
5. Eliminare il pod
6. Verificare persistenza

## Success Criteria

I dati devono essere ancora presenti.
