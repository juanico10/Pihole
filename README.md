# Pihole
El proyecto Pi-hole® es para bloqueo de anuncios en toda la red a través de su propio hardware Linux. Pi-hole® es un sumidero de DNS que protege sus dispositivos de contenidos no deseados sin necesidad de instalar ningún software del lado del cliente.

#

<p align="center">
    <a href="https://pi-hole.net/">
        <img src="https://github.com/JuanRodenas/Pihole/blob/main/pihole.png" alt="Pi-hole">
    </a>
    <br>
    <strong>Network-wide ad blocking via your own Linux hardware</strong>
</p>
<!-- markdownlint-enable MD033 -->

#

📁 [Documentación oficial](https://docs.pi-hole.net/)

## INSTALAR DOCKER-COMPOSE.YML DE PIHOLE
Edit the following variables, with the correct interface and IP.
> Descargar [docker-compose.yml](https://github.com/JuanRodenas/Pihole/blob/main/docker-compose.yml)
>~~~
>INTERFACE:
>ServerIP:
>WEBPASSWORD:
>~~~

#### Running
~~~
docker-compose up -d
~~~

#### Check
~~~
docker ps -a
~~~

Edit the following variables, with the correct interface and IP.

#### Password acceso web
Accedemos al contenedor:
~~~
docker exec -u root -t -i pihole /bin/bash
~~~
Cambiamos la password:
~~~
pihole -a -p
~~~

#### Acceso al dashboard
Hay varias formas de acceder al dashboard [access the dashboard](https://discourse.pi-hole.net/t/how-do-i-access-pi-holes-dashboard-admin-interface/3168):

1. `http://pi.hole/admin/` (when using Pi-hole as your DNS server)
2. `http://<IP_ADDPRESS_OF_YOUR_PI_HOLE>/admin/`
3. `http://pi.hole/` (when using Pi-hole as your DNS server)


# Listas para Pihole

## Main White Lists

| List | Link | Description |
| -- | -- | -- |
| Whitelist | [Link](https://raw.githubusercontent.com/anudeepND/whitelist/master/domains/whitelist.txt) | Lista blanca a permitir |


## Main Black Lists

| List | Link | Description |
| -- | -- | -- |
| dbl.oisd | [Link](https://dbl.oisd.nl) | - |
| cameleon | [Link](https://sysctl.org/cameleon/hosts) | - |
| simple_ad | [Link](https://s3.amazonaws.com/lists.disconnect.me/simple_ad.txt) | To Block simple_ad |
| hosts | [Link](http://winhelp2002.mvps.org/hosts.txt) | - |
| malvertising | [Link](https://s3.amazonaws.com/lists.disconnect.me/simple_malvertising.txt) | To Block malvertising |
| hosts | [Link](https://someonewhocares.org/hosts/hosts) | - |
| AdAway | [Link](https://adaway.org/hosts.txt) | - |
| Easyprivacy | [Link](https://v.firebog.net/hosts/Easyprivacy.txt) | - |
| AdguardDNS | [Link](https://v.firebog.net/hosts/AdguardDNS.txt) | To Block AdguardDNS |
| Easylist | [Link](https://v.firebog.net/hosts/Easylist.txt) | To Block Easylist |
| SmartTV | [Link](https://raw.githubusercontent.com/Perflyst/PiHoleBlocklist/master/SmartTV.txt) | To Block SmartTV |
| phishing | [Link](https://phishing.army/download/phishing_army_blocklist_extended.txt) | To Block phishing |
| Spam | [Link](https://raw.githubusercontent.com/Spam404/lists/master/main-blacklist.txt) | To Block Spam |
| trackers | [Link](https://hostfiles.frogeye.fr/firstparty-trackers-hosts.txt) | To Block trackers |
| hosts_browser | [Link](https://zerodot1.gitlab.io/CoinBlockerLists/hosts_browser) | - |
| add.Risk | [Link](https://raw.githubusercontent.com/FadeMind/hosts.extras/master/add.Risk/hosts) | - |
| adservers | [Link](https://raw.githubusercontent.com/anudeepND/blacklist/master/adservers.txt) | To Block adservers |
| ads-and-tracking-extended | [Link](https://www.github.developerdan.com/hosts/lists/ads-and-tracking-extended.txt) | - |
| WindowsSpyBlocker | [Link](https://raw.githubusercontent.com/crazy-max/WindowsSpyBlocker/master/data/hosts/spy.txt) | To Block WindowsSpyBlocker |
| StevenBlack | [Link](https://raw.githubusercontent.com/StevenBlack/hosts/master/hosts) | To Block StevenBlack |
| urlhaus-filter-domains | [Link](https://raw.githubusercontent.com/AzagraMac/PiHoleDocker/master/list/urlhaus-filter-domains.txt) | - |
| everything | [Link](https://blocklistproject.github.io/Lists/everything.txt) | To Block everything |
| youtube | [Link](https://raw.githubusercontent.com/blocklistproject/Lists/master/youtube.txt) | To Block youtube |
| outapzazaList | [Link](https://raw.githubusercontent.com/AzagraMac/PiHoleDocker/master/list/outapzazaList.txt) | - |
| NSABlocklist | [Link](https://raw.githubusercontent.com/AzagraMac/PiHoleDocker/master/list/NSABlocklist.txt) | - |
| adblock-nocoin | [Link](https://raw.githubusercontent.com/hoshsadiq/adblock-nocoin-list/master/hosts.txt) | To Block adblock |
| AndroidTracking | [Link](https://raw.githubusercontent.com/AzagraMac/PiHoleDocker/master/list/AndroidTracking.txt) | To Block AndroidTracking |
| Prigent-Ads | [Link](https://v.firebog.net/hosts/Prigent-Ads.txt) | To Block Prigent-Ads |
| spammers | [Link](https://raw.githubusercontent.com/matomo-org/referrer-spam-blacklist/master/spammers.txt) | To Block spammers | 
| adguard | [Link](https://raw.githubusercontent.com/Zelo72/adguard/main/d3host.adblock) | To Block adguard |
| GoodbyeAds-Ultra | [Link](https://raw.githubusercontent.com/jerryn70/GoodbyeAds/master/Hosts/GoodbyeAds-Ultra.txt) | To Block GoodbyeAds |
| AdBlock | [Link](https://raw.githubusercontent.com/notracking/hosts-blocklists/master/adblock/adblock.txt) | To Block AdBlock |
| Facebook | [Link](https://github.com/jmdugan/blocklists/blob/master/corporations/facebook/all) | To Block Facebook/Instagram/Whatsapp |
| Whatsapp open | [Link](https://raw.githubusercontent.com/jmdugan/blocklists/master/corporations/facebook/all-but-whatsapp) | To Block Facebook/Instagram but leave Whatsapp open |
| Google | [Link](https://raw.githubusercontent.com/jmdugan/blocklists/master/corporations/google/all) | To Block Google |
| Mozilla | [Link](https://raw.githubusercontent.com/jmdugan/blocklists/master/corporations/mozilla/all) | To Block Mozilla tracking |
| Microsoft | [Link](https://raw.githubusercontent.com/jmdugan/blocklists/master/corporations/microsoft/all) | To Block Microsoft |


# Regenerar listas
Accedemos al contenedor:
~~~
docker exec -u root -t -i pihole /bin/bash
~~~
Regeneramos las listas:
~~~
pihole -g
~~~

## Ready!
