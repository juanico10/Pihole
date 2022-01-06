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

| List | Link | AdGuard | Description |
| -- | :--: | :--: | -- |
| Whitelist | [Link](https://raw.githubusercontent.com/anudeepND/whitelist/master/domains/whitelist.txt) | - | Lista blanca a permitir |


## Main Black Lists

| List | Link | AdGuard | Description |
| -- | :--: | :--: | -- |
| Listas oisd | [Link](https://dbl.oisd.nl) | [Link](https://abp.oisd.nl) | To Block host Adguard and domains [dbl.oisd](https://oisd.nl/) |
| SmartTV | [Link](https://raw.githubusercontent.com/Perflyst/PiHoleBlocklist/master/SmartTV.txt) | [Link](https://raw.githubusercontent.com/blocklistproject/Lists/master/adguard/smart-tv-ags.txt) | To Block SmartTV |
| WindowsSpyBlocker | [Link](https://raw.githubusercontent.com/crazy-max/WindowsSpyBlocker/master/data/hosts/spy.txt) | - | To Block WindowsSpyBlocker |
| urlhaus-filter-domains | [Link](https://raw.githubusercontent.com/AzagraMac/PiHoleDocker/master/list/urlhaus-filter-domains.txt) | - | - |
| Malware | [Link](https://blocklistproject.github.io/Lists/malware.txt) | [Link](https://raw.githubusercontent.com/blocklistproject/Lists/master/adguard/malware-ags.txt) | To Block malware |
| Ransomware | [Link](https://raw.githubusercontent.com/blocklistproject/Lists/master/ransomware.txt) | [Link](https://raw.githubusercontent.com/blocklistproject/Lists/master/adguard/ransomware-ags.txt) | To Block ransomware |
| everything | [Link](https://blocklistproject.github.io/Lists/everything.txt) | [Link](https://raw.githubusercontent.com/blocklistproject/Lists/master/adguard/everything-ags.txt) | To Block everything |
| energized pro | [Link](https://energized.pro/unified/formats/hosts.txt) | [Link]() | To Block [energized](https://energized.pro/) |
| Gambling-porn | [Link](https://raw.githubusercontent.com/JuanRodenas/Pi-hole_list/main/List/Gambling.txt) | [Link](https://github.com/blocklistproject/Lists/blob/master/adguard/gambling-ags.txt) | To Block Gambling and porn |
| TrackingAds | [Link](https://raw.githubusercontent.com/JuanRodenas/Pi-hole_list/main/List/TrackingAds.txt) | - | To Block Tracking, Ads and spammers |
| Adblock_Plus | - | [Link](https://raw.githubusercontent.com/JuanRodenas/Pi-hole_list/main/List/Adblock_Plus_Ads.txt) | To Block Adblock_Plus |
| VideoGamesAdiction | [Link](https://raw.githubusercontent.com/JuanRodenas/Pi-hole_list/main/List/VideoGamesAdiction.txt) | - | To Block VideoGames Adiction |
| AndroidTracking | [Link](https://raw.githubusercontent.com/AzagraMac/PiHoleDocker/master/list/AndroidTracking.txt) | - | To Block AndroidTracking |
| Youtube | [Link](https://raw.githubusercontent.com/blocklistproject/Lists/master/youtube.txt) | [Link](https://raw.githubusercontent.com/blocklistproject/Lists/master/adguard/youtube-ags.txt) | To Block youtube |
| Facebook | [Link](https://github.com/jmdugan/blocklists/blob/master/corporations/facebook/all) | - | To Block Facebook/Instagram/Whatsapp |
| Whatsapp open | [Link](https://raw.githubusercontent.com/jmdugan/blocklists/master/corporations/facebook/all-but-whatsapp) | - | To Block Facebook/Instagram but leave Whatsapp open |
| Google | [Link](https://raw.githubusercontent.com/jmdugan/blocklists/master/corporations/google/all) | - | To Block Google |
| Mozilla | [Link](https://raw.githubusercontent.com/JuanRodenas/Pi-hole_list/main/List/mozilla.txt) | [Link](https://raw.githubusercontent.com/JuanRodenas/Pi-hole_list/main/List/mozilla_adguard.txt) | To Block Mozilla tracking |
| Microsoft | [Link](https://raw.githubusercontent.com/jmdugan/blocklists/master/corporations/microsoft/all) | - | To Block Microsoft |

## Comprobar tu SelfHosted:

<details>
<summary>fivefilters:</summary>

<Original>&nbsp;Pagina para comprobar tu selfhosted de fivefilters</Original>

<p>  &nbsp;&nbsp;https://blockads.fivefilters.org/</p>
</details>
&nbsp;

<details>
<summary>d3ward:</summary>

<Original>&nbsp;Pagina para comprobar tu selfhosted de [d3ward](https://d3ward.github.io/toolz/)</Original>

<p>  &nbsp;&nbsp;https://d3ward.github.io/toolz/adblock.html</p>
</details>
&nbsp;

<details>
<summary>canyoublockit:</summary>

<Original>&nbsp;Pagina para comprobar tu selfhosted de canyoublockit</Original>

<p>  &nbsp;&nbsp;https://canyoublockit.com/</p>
</details>
&nbsp;

## Comprobar DoH, DoT y DDNSSEC:

<details>
<summary>1.1.1.1 de Cloudflare:</summary>

<Original>&nbsp;Pagina para comprobar cifrado de 1.1.1.1 de Cloudflare</Original>

<p>  &nbsp;&nbsp;https://1.1.1.1/help</p>
</details>
&nbsp;

<details>
<summary>Tenta VPN Browser:</summary>

<Original>&nbsp;Pagina para comprobar cifrado de Tenta VPN Browser</Original>

<p>  &nbsp;&nbsp;https://tenta.com/test/</p>
</details>
&nbsp;

<details>
<summary>Cloudflare:</summary>

<Original>&nbsp;Pagina para comprobar cifrado de Cloudflare</Original>

<p>  &nbsp;&nbsp;https://www.cloudflare.com/es-es/ssl/encrypted-sni/</p>
</details>
&nbsp;

<details>
<summary>DNSSEC Resolver Test:</summary>

<Original>&nbsp;Pagina para comprobar cifrado DNSSEC por Matthäus Wander</Original>

<p>  &nbsp;&nbsp;http://dnssec.vs.uni-due.de/</p>
<p>  &nbsp;&nbsp;http://www.dnssec-or-not.com/</p>
<p>  &nbsp;&nbsp;http://en.conn.internet.nl/connection/</p>
</details>
&nbsp;


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
