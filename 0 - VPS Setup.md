
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
sudo apt install qbittorrent-nox
```
```
sudo apt update
```

```
sudo adduser --system --group qbittorrent-nox
```
```
sudo adduser your-username qbittorrent-nox
```
```
sudo nano /etc/systemd/system/qbittorrent-nox.service
```
```
[Unit]
Description=qBittorrent Command Line Client
After=network.target
[Service]
#Do not change to "simple"
Type=forking
User=qbittorrent-nox
Group=qbittorrent-nox
UMask=007
ExecStart=/usr/bin/qbittorrent-nox -d --webui-port=8080
Restart=on-failure
[Install]
WantedBy=multi-user.target
```
```
sudo systemctl start qbittorrent-nox
```

Note that if you change a systemd service file, you need to reload the systemd daemon for the
change to take effect.
```
sudo systemctl daemon-reload
```

Enable auto start at system boot time
```
sudo systemctl enable qbittorrent-nox
```

Check the status
```
systemctl status qbittorrent-nox
```
To access the qBittorrent Web UI from local network, enter the Ubuntu server’s private IP address
followed by the port number like ```192.168.0.102:8080```

Username is ```admin```. Default password is ```adminadmin```.

Change the default username and password. Go to ```Tools``` > ```Options```


### Enable HTTPS to Encrypt Communications

To secure the Web UI, you can install a free TLS certificate issued by Let’s Encrypt. First you need to install the Let’s Encrypt client (certbot)
```
sudo add-apt-repository ppa:certbot/certbot
```
```
sudo apt install certbot python3-certbot-nginx
```

```Python3-certbot-nginx``` is the Certbot Nginx plugin. After they are installed, run the following
command to automatically obtain and install Let’s Encrypt certificate.
```
sudo certbot --nginx --redirect --agree-tos --hsts --staple-ocsp --email your-email-address -d torrent.your-domain.com
```


## Jellyfin
Pour obtenir des paquets via un protocole sécurisé, il faut d'abord activer sa prise en charge à l'aide de la commande ci-dessous :
```
sudo apt install apt-transport-https ca-certificates gnupg2 curl git -y
```
Ajout de la clé gpg
```
wget -O- https://repo.jellyfin.org/jellyfin_team.gpg.key | sudo apt-key add -
```
Update
```
sudo apt update
```
Installation de Jellyfin (il se trouve sur le port 8086 par defaut)
```
sudo apt install jellyfin
```
Activation et lancement de Jellyfin
```
sudo systemctl enable jellyfin
```
```
sudo systemctl start jellyfin
```
Vérification s'il fonctionne correctement
```
sudo systemctl status jellyfin --no-pager -l
```
Si on utilise un Firewall comme ufw, on peut lui ajouter une exception pour le port 8086
```
sudo ufw allow 8096
```
