
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
apt install docker.io
```
 (peut-être autre chose que docker.io, selon la version de ubuntu)
 
## Installation nginx
```python
docker run -d -p 80:80 nginx:latest
```
