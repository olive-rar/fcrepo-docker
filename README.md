# Fedora Repository 5 Docker & Kubernetes

Inspired by fcrepo4-labs/fcrepo4-docker

## Docker

### Run Fedora
```
### Start server
docker-compose up -d

### Shutdown server
docker-compose down
```
### Run Fedora with a MySQL database:
```
### Start server
docker-compose -f fcrepo-mysql.yml up -d

### Shutdown server
docker-compose -f fcrepo-mysql.yml down
```
### Run Fedora with a PostgreSQL database:
```
# Start server
docker-compose -f fcrepo-postgres.yml up -d

# Shutdown server
docker-compose -f fcrepo-postgres.yml down
```

Fedora [Dockerfile](docker/services/fcrepo/Dockerfile)

## Kubernetes
