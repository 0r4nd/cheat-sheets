
# docker

stop all containers
```shell
docker kill $(docker ps -q)
```
remove all containers
```shell
docker rm $(docker ps -a -q)
```
remove all images
```shell
docker rmi $(docker images -q)
```
remove all networks
```shell
docker network prune
```
remove all volumes
```shell
docker volume prune
```

## Debug / Logs

check logs of a container
```shell
docker logs --since=20m ${PWD##*/}-db-1
```
check logs of the last build
```shell
docker compose logs
```
interactive shell (after docker compose up -d)
```shell
docker-compose exec nginx sh
```

## Build

build docker compose basic
```shell
docker compose up -d --build 
```
build docker compose with file
```shell
docker compose -f docker-compose.dev.yml down --volumes
```

## DataBase

enter database container (with psql)
```shell
docker exec -it ${PWD##*/}-db-1 psql -U postgres
```
postgres volume backup (must be in the docker-compose directory)
```shell
VOL=${PWD##*/}_pgdata
DST=backup_${VOL}_$(date +%Y-%m-%d--%H.%M.%S).tar.gz
docker run --rm -v "${VOL}:/data" -v "${PWD}:/backup-dir" ubuntu tar cvzf /backup-dir/${DST} /data
```
postgres volume restore (must be in the docker-compose directory)
```shell
SRC=backup_test_pgdata_2024-09-03--21.27.51.tar.gz
VOL=${PWD##*/}_pgdata
docker run --rm -v "${VOL}:/data" -v "${PWD}:/backup-dir" ubuntu bash -c "rm -rf /data/{*,.*}; cd /data && tar xvzf /backup-dir/${SRC} --strip 1"
```

## Health Status

check health status of "db" service
```shell
docker inspect --format "{{.State.Health.Status}}" $(docker compose ps -q db)
```








