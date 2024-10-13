#### MY01 Mask Websocket Server

## Part 0. Env
Catzillaw
sspnxlhp
33553
/chillbababoom

## Part 1. Setup server

##### adduser
```
#!/bin/bash

USER=harodonw

sudo useradd -s /bin/bash -d /home/${USER}/ -m -G sudo ${USER}
sudo passwd ${USER}
```

##### Upgrade
```
sudo apt update && upgrade -y
```

##### SSHD - set port for SSHD
```
netstat -tan
systemctl restart sshd
mkdir .ssh | cd .ssh | touch authorized_keys

```
![Alt text](img/image.png)


##### docker
```
#!/bin/bash

# Предварительно установим набор пакетов, необходимый для доступа к репозиториям по протоколу HTTPS:

#     apt-transport-https — активирует передачу файлов и данных через https;
#     ca-сertificates — активирует проверку сертификаты безопасности;
#     curl — утилита для обращения к веб-ресурсам;
#     software-properties-common — активирует возможность использования скриптов для управления программным обеспечением.
sudo apt update
sudo apt install apt-transport-https ca-certificates curl software-properties-common

# добавим в систему GPG-ключ для работы с официальным репозиторием Docker
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"

# начинаем установку
sudo apt update
sudo apt install docker-ce -y
sudo systemctl start docker
sudo systemctl enable docker

USER=harodonw

sudo usermod -aG docker ${USER}
su - ${USER}
cat /etc/passwd | grep ${USER}
```

##### docker-compose
```
#!/bin/bash


sudo curl -L "https://github.com/docker/compose/releases/download/v2.12.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
sudo apt-get install docker-compose
```

## Part 2. SSL
https://youtu.be/4BcK_2-0grQ

<!-- Generate self-signed certificate
```
openssl req -x509 -keyout /etc/ssl/certs/3x-ui.key -out /etc/ssl/certs/3x-ui.pem -newkey rsa:4096 -sha256 -days 3650 -nodes -new
```
Generate self-signed certificate with Subject Alternative Name
```
openssl req -x509 -keyout /etc/ssl/certs/3x-ui.key -out /etc/ssl/certs/3x-ui.pem -newkey rsa:4096 -sha256 -days 3650 -nodes -new -addext "subjectAltName=DNS:*.domain.com"
```
Show fingerprint of certificate
```
openssl x509 -noout -sha256 -fingerprint -in /etc/ssl/certs/3x-ui.pem
```
sha256 Fingerprint=46:20:0D:90:C1:15:3A:DA:52:A1:69:F9:95:52:E8:E4:94:66:4C:19:91:AC:1E:A6:98:1C:82:34:73:F4:77:6C -->
```
openssl req -x509 -newkey rsa:4096 -nodes -sha256 -keyout private.key -out public.key -days 3650 -subj "/CN=APP"
docker cp private.key 3x-ui:private.key
docker cp public.key 3x-ui:public.key
```


## Part 3. 3X-UI
```
git clone https://github.com/MHSanaei/3x-ui.git

nano docker-compose.yml

 # было:  image: ghcr.io/mhsanaei/3x-ui:latest
 # стало: image: ghcr.io/mhsanaei/3x-ui:v2.0.2
 
docker-compose up -d

```

## Part 4. WARP
https://youtu.be/44BSRofsuBY

```

```

## Part 5. Fail2Ban
```

```

## Part 6. CLOUDFARE ^^ DOMEN
```

```

## Part 7. IPtables

https://losst.pro/nastrojka-iptables-dlya-chajnikov

https://www.dmosk.ru/instruktions.php?object=iptables-settings

```

```

## Part 8. CLIENT
```

```