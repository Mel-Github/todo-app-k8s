# todo-app-k8s
Kubernetes Depoyment Files

Kubernetes files for deploying the Todo application. 

# Pre-Requisite

* Create the Servian namespace. 
* All k8s objects are in the Servian namespace.
* Ensure there is connectivity to Docker Hub.

## PVC Creation

Depending on your k8s environment, the PVC creation method vary. Adjust the yaml accordingly to your environment.

[Sample PVC here](https://kubernetes.io/docs/tasks/configure-pod-container/configure-persistent-volume-storage/#create-a-persistentvolumeclaim)

```yaml
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: postgres-service
spec:
  storageClassName: manual
  accessModes:
    - ReadWriteOnce
  resources:
    requests:
      storage: 1Gi
```
## Deployment Steps



* kubectl create ns servian
* Deploy the  PersistentVolumeClaim yaml
* kubectl create secret -f postgres-db-secret.yaml 
* kubectl create postgres.yaml
* kubectl todo-app.yaml
* kubectl postgres-svc.yaml
* kubectl todo-app-svc.yaml
* todo-app-ingress.yaml

