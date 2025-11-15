# Docker Compose Tags

## Servicios

``` .yml
services:
```

Define los servicios que formarán parte de la aplicación.

Cada ```service``` se convierte en un contenedor.

## Imagen

``` .yml
services:
    app:
        image:
```

Indica el nombre y tag a utilizar.

``` .yml
services:
    app:
        image:
        build:
```

Cuando se usa ```build``` se construye el contenedor basado en la imagen de la ruta especificada.

## Puertos

``` .yml
services:
    app:
        ports:
        - host:container
```

Mapea los puertos del host al contenedor. Ejemplo: 3307:3306 --> Host:3307, Contenedor: 3306

## Variables de Entorno

``` .yml
services:
    app:
        environment:
        - NAME=VALUE
```

Define variables de entorno visibles dentro del contenedor. Puede referenciar valores desde .env

## Volúmenes

``` .yml
services:
    app:
        volumes:
            - nombreVolumen:rutaDelContenedor
volumes:
    nombreVolumen:

```

Volúmenes que persisten info fuera del ciclo de vida del contenedor.

## Secretos

Para la creación de secretos en línea usé los siguientes comandosÑ

``` bash
printf "puertoElegido" | docker secret create db_port -
printf "UsuarioBaseDeDatos" | docker secret create db_user -
printf "PasswordSeguro" | docker secret create db_password -
printf "nestapp_db" | docker secret create db_name -
```
