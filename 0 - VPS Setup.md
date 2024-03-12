
## Accès serveur par ssh (port 22 par default)
```
ssh root@xx.xx.xx.xx
```

## Update
```
sudo apt update
```
```
sudo apt upgrade
```

## Changer le port ssh
```
cd ..
```
```
nano /etc/ssh/sshd_config
```
```
/etc/init.d/ssh restart
```
(relancer la session avec ctrl+d)

## Installation docker
```
apt install docker
```
```
docker -v
```
```
apt install docker.io  (peut-être autre chose que docker.io, selon la version de ubuntu)
```

## Vérification docker, puis suppression de l'image
```
docker run hello-world
```
```
docker ps -a
```
```
docker rm "id du container"
```

## Installation docker-compose
```
apt install docker-compose
```

## Installation nginx
```
docker run -d -p 80:80 nginx:latest
```

# Options

## Seedbox
```
sudo apt install software-properties-common
```
```
sudo add-apt-repository ppa:qbittorrent-team/qbittorrent-stable
```
```
sudo apt update
```










