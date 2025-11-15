# Imágenes y Dockerfile

## Imagen

Es una plantilla inmutable que contiene todo lo necesario para ejecutar una aplicación, incluido el código.

- No cambia una vez creada. Si hago un cambio sobre el archivo, en realidad he creado una nueva imagen.
- Se construye en capas, cada comando es una nueva capa.
- Tenemos la posibilidad de compartirlas a través de un Registry

## Dockerfile

Un archivo de texto que contiene las definiciones para construir la imagen (a través de comandos)

### Comandos

**FROM:** Define la imagen base para nuestra imagen. SE USA UNA ÚNICA VEZ

**WORKDIR:** Define el directorio o carpeta de trabajo dentro del contenedor, SE PUEDE USAR MÁS DE UNA VEZ.

**COPY:** Copiar archivos desde la máquina host hacia la imagen en el momento de la construcción.

**RUN:** Ejecuta comandos en tiempo de construcción.

**EXPOSE:** Indica el puerto que el contenedor usará, esto es meramente informativo. SE PUEDE USAR MÁS DE UNA VEZ.

**CMD:** Define el comando que se ejecutará al iniciar el contenedor. SE USA UNA SOLA VEZ

**ENTRYPOINT:** Define el comando que se ejecutará al iniciar el contenedor. SE USA UNA SOLA VEZ

## Construir imágebes con Docker

Solo necesitamos un archivo Dockerfile, nos posicionamos en la ruta del mismo desde la terminal y ejecutamos el siguiente comando:

``` shell
docker image build --tag [nombre:tag] [ruta del archivo Dockerfile]
```

Si no especificamos un tag se crea por defecto con el tag :latest
