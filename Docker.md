
## Docker

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
