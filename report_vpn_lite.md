#### MY01 Mask Websocket Server

## Part 0. Env
Your Panel Port is: 33553
Your Username will be generated randomly: 2rd6WGhg4k
Your Password will be generated randomly: bmRqY1qgyT
Your Web Base Path will be generated randomly: appeuujEcLm8Fkj

catzillaw
sspnxlhp
/chillbababoom/

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


## Part 2. SSL
https://youtu.be/4BcK_2-0grQ

Generate self-signed certificate
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

sha256 Fingerprint=70:4F:B4:27:51:A2:A2:5A:50:69:EC:E3:72:D9:86:C2:C0:35:99:EE:59:A9:C0:E2:1D:5F:B7:A8:C2:B8:66:18


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
installed on 3x-ui
```

## Part 6. CLOUDFARE ^^ DOMEN
```
need buying domen
```

## Part 7. IPtables

https://losst.pro/nastrojka-iptables-dlya-chajnikov

https://www.dmosk.ru/instruktions.php?object=iptables-settings

```

```

## Part 8. CLIENT
```

```