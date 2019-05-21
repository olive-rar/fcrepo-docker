# Fedora Repository 5 Docker & Kubernetes

## Docker

### Docker image


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
