# Pihole
Proyecto para catalogar y enumerar los nombres de dominio bloquear en Pihole.

![alt text](https://github.com/JuanRodenas/Pihole/blob/main/pihole.png)


# INSTALAR DOCKER
Primero, actualice su lista de paquetes existente: 
~~~
sudo apt update
~~~

A continuación, instale algunos paquetes de requisitos previos que permitan a apt usar paquetes a través de HTTPS: 
~~~
sudo apt install apt-transport-https ca-certificates curl software-properties-common
~~~

Luego, añada la clave de GPG para el repositorio oficial de Docker en su sistema: 
~~~
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
~~~

Agregue el repositorio de Docker a las fuentes de APT: 
~~~
sudo add-apt-repository `deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable`
~~~

A continuación, actualice el paquete de base de datos con los paquetes de Docker del repositorio recién agregado: 
~~~
sudo apt update
~~~

Por último, instale Docker: 
~~~
sudo apt install docker-ce
~~~

Compruebe que funcione: 
~~~
sudo systemctl status docker
~~~

Ejecutar el comando Docker sin sudo, si desea evitar escribir sudo al ejecutar el comando docker, agregue su nombre de usuario al grupo docker: 
~~~
sudo usermod -aG docker ${USER}
~~~


# Instalar Docker Compose
El siguiente comando descargará la versión 2.2.2 y guardará el archivo ejecutable en /usr/local/bin/docker-compose, que hará que este software esté globalmente accesible como docker-compose, Si desea descargar la versión más reciente, ir al enlace: https://github.com/docker/compose/releases y modificar la versión:
~~~
sudo curl -L `https://github.com/docker/compose/releases/download/2.2.2/docker-compose-$(uname -s)-$(uname -m)` -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
~~~

Para verificar que la instalación se realizó correctamente, puede ejecutar:
~~~
docker-compose --version
~~~


# INSTALAR DOCKER-COMPOSE.YML DE PIHOLE
Edit the following variables, with the correct interface and IP.
> Descargar [docker-compose.yml](https://github.com/JuanRodenas/Pihole/blob/main/docker-compose.yml)
>~~~
>INTERFACE:
>ServerIP:
>~~~

# Running
~~~
docker-compose up -d
~~~

# Check
~~~
docker ps -a
~~~

Edit the following variables, with the correct interface and IP.

# Password acceso web
Accedemos al contenedor:
~~~
docker exec -u root -t -i nextcloud /bin/bash
~~~
Cambiamos la password:
~~~
pihole -a -p
~~~

# Listas para Pihole

## Main White Lists


## Main black Lists
~~~
https://dbl.oisd.nl 
~~~
~~~
https://sysctl.org/cameleon/hosts 
~~~
~~~
https://s3.amazonaws.com/lists.disconnect.me/simple_tracking.txt 
~~~
~~~
https://s3.amazonaws.com/lists.disconnect.me/simple_ad.txt 
~~~
~~~
http://winhelp2002.mvps.org/hosts.txt 
~~~
~~~
https://s3.amazonaws.com/lists.disconnect.me/simple_malvertising.txt 
~~~
~~~
https://someonewhocares.org/hosts/hosts 
~~~
~~~
https://adaway.org/hosts.txt 
~~~
~~~
https://pgl.yoyo.org/adservers/serverlist.php?hostformat=hosts&showintro=0&mimetype=plaintext 
~~~
~~~
https://v.firebog.net/hosts/Easyprivacy.txt 
~~~
~~~
https://v.firebog.net/hosts/AdguardDNS.txt 
~~~
~~~
https://v.firebog.net/hosts/Easylist.txt 
~~~
~~~
https://raw.githubusercontent.com/Perflyst/PiHoleBlocklist/master/AmazonFireTV.txt 
~~~
~~~
https://raw.githubusercontent.com/Perflyst/PiHoleBlocklist/master/SmartTV.txt 
~~~
~~~
https://phishing.army/download/phishing_army_blocklist_extended.txt 
~~~
~~~
https://raw.githubusercontent.com/Spam404/lists/master/main-blacklist.txt 
~~~
~~~
https://hostfiles.frogeye.fr/firstparty-trackers-hosts.txt 
~~~
~~~
https://zerodot1.gitlab.io/CoinBlockerLists/hosts_browser 
~~~
~~~
https://raw.githubusercontent.com/FadeMind/hosts.extras/master/add.Spam/hosts 
~~~
~~~
https://raw.githubusercontent.com/FadeMind/hosts.extras/master/UncheckyAds/hosts 
~~~
~~~
https://raw.githubusercontent.com/FadeMind/hosts.extras/master/add.Risk/hosts 
~~~
~~~
https://raw.githubusercontent.com/anudeepND/blacklist/master/adservers.txt 
~~~
~~~
https://www.github.developerdan.com/hosts/lists/ads-and-tracking-extended.txt 
~~~
~~~
https://raw.githubusercontent.com/crazy-max/WindowsSpyBlocker/master/data/hosts/spy.txt 
~~~
~~~
https://raw.githubusercontent.com/StevenBlack/hosts/master/hosts 
~~~
~~~
https://raw.githubusercontent.com/AzagraMac/PiHoleDocker/master/list/urlhaus-filter-domains.txt 
~~~
~~~
https://raw.githubusercontent.com/kboghdady/youTube_ads_4_pi-hole/master/youtubelist.txt 
~~~
~~~
https://raw.githubusercontent.com/AzagraMac/PiHoleDocker/master/list/outapzazaList.txt 
~~~
~~~
https://raw.githubusercontent.com/outapzaza/blocklist/master/fingerprintblock.txt 
~~~
~~~
https://raw.githubusercontent.com/outapzaza/blocklist/master/serverblocklist.txt 
~~~
~~~
https://raw.githubusercontent.com/AzagraMac/PiHoleDocker/master/list/NSABlocklist.txt 
~~~
~~~
https://raw.githubusercontent.com/hoshsadiq/adblock-nocoin-list/master/hosts.txt 
~~~
~~~
https://raw.githubusercontent.com/AzagraMac/PiHoleDocker/master/list/AndroidTracking.txt 
~~~
~~~
https://v.firebog.net/hosts/Prigent-Ads.txt 
~~~
~~~
https://raw.githubusercontent.com/matomo-org/referrer-spam-blacklist/master/spammers.txt 
~~~
~~~
https://raw.githubusercontent.com/Zelo72/adguard/main/d3host.adblock
~~~
~~~
https://raw.githubusercontent.com/jerryn70/GoodbyeAds/master/Hosts/GoodbyeAds-Ultra.txt
~~~
~~~
https://github.com/jmdugan/blocklists/blob/master/corporations/facebook/all
~~~
~~~
https://raw.githubusercontent.com/jmdugan/blocklists/master/corporations/google/all
~~~
~~~
https://raw.githubusercontent.com/jmdugan/blocklists/master/corporations/mozilla/all
~~~
~~~
https://raw.githubusercontent.com/notracking/hosts-blocklists/master/adblock/adblock.txt
~~~

# Regenerar listas
Accedemos al contenedor:
~~~
docker exec -u root -t -i nextcloud /bin/bash
~~~
Regeneramos las listas:
~~~
pihole -g
~~~

## Ready!
