\# Servidor Web Nginx con Docker Compose



Servidor web nginx ejecutandose localmente en un contenedor Docker, sirviendo contenido estatico desde el directorio `src`.



\## Requisitos



\- Docker

\- Docker Compose v2



\## Estructura



| Ruta                 | Descripcion                      |

|----------------------|----------------------------------|

| `src/index.html`     | Pagina servida por nginx         |

| `conf/default.conf`  | Configuracion del servidor       |

| `docker-compose.yml` | Definicion del servicio          |



\## Uso



Iniciar el contenedor:



```bash

docker compose up -d

```



Verificar el estado:



```bash

docker compose ps

```



Probar el servidor:



```bash

curl http://localhost:8080

```



Tambien se puede abrir http://localhost:8080 en el navegador.



Ver los logs:



```bash

docker compose logs -f web

```



Detener y eliminar el contenedor:



```bash

docker compose down

```



\## Detalles tecnicos



\- Imagen: `nginx:1.27-alpine`

\- Puerto expuesto: `8080` (host) hacia `80` (contenedor)

\- Volumen: `./src` montado en `/usr/share/nginx/html` en modo solo lectura

\- Reinicio automatico: `unless-stopped`

\- Healthcheck cada 30 segundos

