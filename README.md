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

## Detalles
Estas listas se crearon porque quería algo con un poco más de control sobre lo que se bloquea. Muchas listas son de todo o nada. Nos propusimos crear listas con más control sobre lo que se bloquea.

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
