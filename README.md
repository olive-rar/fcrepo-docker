# Fedora Repository 5 in Docker & Kubernetes

https://duraspace.org/fedora/

## Docker

### Run Fedora Repository
```
### Start server
docker-compose -f docker/docker-compose.yaml up -d

### Shutdown server
docker-compose -f docker/docker-compose.yaml down
```
### Run Fedora with a PostgreSQL database:
```
# Start server
docker-compose -f docker/fcrepo-postgres.yml up -d

# Shutdown server
docker-compose -f docker/fcrepo-postgres.yml down
```
### Run Fedora Repository with a MySQL database:
```
### Start server
docker-compose -f docker/fcrepo-mysql.yml up -d

### Shutdown server
docker-compose -f docker/fcrepo-mysql.yml down
```

## Kubernetes

Fedora Repository with PostgreSQL in Kubernetes Cluster.

### Create Namespace
```
kubectl create -f ./kubernetes/fcrepo-namespace.yaml
```

### Create PostgreSQL environment
```
kubectl create -f ./kubernetes/fcrepo-pg-pvc.yaml
kubectl create -f ./kubernetes/fcrepo-postgres-secret.yaml
kubectl create -f ./kubernetes/fcrepo-postgres-deployment.yaml
kubectl create -f ./kubernetes/fcrepo-postgres-service.yaml
```

### Create Fedora environment
```
kubectl create -f ./kubernetes/fcrepo-pvc.yaml
kubectl create -f ./kubernetes/fcrepo-deployment.yaml
kubectl create -f ./kubernetes/fcrepo-service.yaml
```
