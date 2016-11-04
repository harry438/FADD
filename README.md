# FADD (Fully Automated Docker Deployment)
![](http://i.imgur.com/AvRuVrn.png)
### Features :
- Nginx TLS Reverse-proxy
- Automatic Let's Encrypt support
- SNI Multi-Domain support
- Multi-image deployment (Wordpress, LEMP, Ghost, Drupal ...)
- Automatic script for launch a deployment



### Scripts :
Easily install Docker and all requirements :
```
cd /opt ; git clone https://github.com/valentin2105/FADD.git ; cd /opt/FADD
vim config.json # Configure FADD
./install_fadd.sh
```

There are some shell scripts to manage your Docker Host :
- `add_stack.sh` - Deploy an image from the hub and a Nginx TLS vhost.
- `add_domain.sh` - Deploy a Nginx TLS vhost for a specified port.
- `delete_stack.sh` - Delete stack, certs & config of the website.
- `renew_certs.sh` - Renew all TLS certs presents on the host.

### Examples :
- Deploy All-in-one Wordpress :

`add_stack.sh --image=wordpress --domain=site01.example.com --expose=8101`

- Run a docker service an expose his port :

`docker run --name nginx -d -p 8080:80 nginx:latest`

`add_domain.sh --security=no --ip=10.0.0.5 --port=8080`

### Requirements :
- Ubuntu (14.04 / 16.04) / Debian 8
- Python2.7
- Docker 1.10+
- Docker-compose
- curl, openssl, jq, wget, netstat ...

### Hub :
- Wordpress (Nginx/PHP7/MariaDB)
- Joomla (Nginx/PHP7/MariaDB)
- Drupal 8 (Nginx/PHP7/SQLite)
- LEMP (Nginx/PHP7/MariaDB) + FTP ?
- Ghost (Nginx, Ghost JS)
- Wekan (Nginx, Wekan MeteorJS)

## https://fadd.opsnotice.xyz
