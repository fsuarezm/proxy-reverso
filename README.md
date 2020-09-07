![License MIT](https://img.shields.io/badge/license-MIT-blue.svg)

## Proxy-reverse

Proxy reverso para desarrollo.

### Uso

Configurar el archivo `.env` utilizando como modelo `.env.example`:

    PROXY_NETWORK=red_docker_compartida

Ejecutar:

    # docker network create red_docker_compartida
    $ docker-compose up -d

Si desea ejecutar un script para iniciar y parar el servicio:

Para levantar el servicio

    # vim /usr/local/bin/proxy-up

Edite el archivo con el siguiente contenido:

    #!/bin/bash
    echo "Iniciando Proxy Apache ..."
    cd /carpeta_proxy_inverso
    docker-compose up -d
    exit
    exec bash
    echo "Proxy Apache iniciado"

Para parar el servicio

    # vim /usr/local/bin/proxy-down

Edite el archivo con el siguiente contenido:

    #!/bin/bash
    echo "Parando Proxy Apache ..."
    cd /carpeta_proxy_inverso
    docker-compose down --remove-orphans
    exit
    exec bash
    echo "Proxy Apache parado"

Finalmente asigne permisos de ejecución:

    # chmod +x /usr/local/bin/proxy-up
    # chmod +x /usr/local/bin/proxy-down

