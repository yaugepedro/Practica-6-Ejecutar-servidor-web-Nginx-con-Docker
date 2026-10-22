# Práctica 6 - Servidor web Nginx con Docker

Yauge Pedro Volquez Terrero

Esta práctica es para correr un servidor Nginx en mi PC usando Docker Compose y que muestre un "Hola Mundo".

## Lo que hice

Primero instalé Docker Desktop en Windows. Me pidió instalar WSL, así que lo instalé y reinicié la PC. Después de eso verifiqué que docker y git funcionaran con `docker --version` y `git --version`.

Luego creé la carpeta `nginx-docker` con dos carpetas adentro: `src` y `conf`.

En `src` puse el `index.html` con el Hola Mundo. En `conf` puse un `default.conf` con la configuración de Nginx.

Después hice el `docker-compose.yml`. Ahí puse la imagen de nginx, el puerto 8080 y los volúmenes. El volumen más importante es el que conecta mi carpeta `src` con `/usr/share/nginx/html`, porque ahí es donde nginx busca la página.

Para levantarlo corrí esto en la carpeta del proyecto:

```
docker compose up -d
```

Con `docker compose ps` vi que el contenedor estaba corriendo, y abrí http://localhost:8080 en el navegador. Salió la página bien.

Por último inicié un repositorio con git y lo subí a GitHub.

## Para probarlo

```
git clone https://github.com/yaugepedro/Practica-6-Ejecutar-servidor-web-Nginx-con-Docker.git
cd Practica-6-Ejecutar-servidor-web-Nginx-con-Docker
docker compose up -d
```

Y abrir http://localhost:8080

Para apagarlo:

```
docker compose down
```
