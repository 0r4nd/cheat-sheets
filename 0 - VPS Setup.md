
## Accès serveur par ssh (port 22 par default)
```python
ssh root@xx.xx.xx.xx
```

## Update
```python
sudo apt update
```
```python
sudo apt upgrade
```

## Changer le port ssh
```python
cd ..
```
```python
nano /etc/ssh/sshd_config
```
```python
/etc/init.d/ssh restart
```
(relancer la session avec ctrl+d)

## Installation docker
```python
apt install docker
```
```python
docker -v
```
```python
apt install docker.io  (peut-être autre chose que docker.io, selon la version de ubuntu)
```

## Vérification docker, puis suppression de l'image
```python
docker run hello-world
```
```python
docker ps -a
```
```python
docker rm "id du container"
```

## Installation docker-compose
```python
apt install docker-compose
```

## Installation nginx
```python
docker run -d -p 80:80 nginx:latest
```
