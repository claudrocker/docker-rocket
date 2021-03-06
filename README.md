# docker-tips
Lista de comandos Docker más usados

## Instalar docker (debian jessie)
Mas info en: https://docs.docker.com/engine/installation/linux/debian/

1. Instalar packages
```
$ apt-get install \
     apt-transport-https \
     ca-certificates \
     curl \
     gnupg2 \
     software-properties-common
```

2. Agregar key
```     
$ curl -fsSL https://download.docker.com/linux/debian/gpg | apt-key add -
```

3. Agregar repositorio de docker
```
add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/debian \
   $(lsb_release -cs) \
   stable"
```

4. Actualizar repositorios de apt-get
```
apt-get update
```

5. Instalar docker
```
apt-get install docker-ce
```

6. Verificar con: 
```
docker --version
```

## Comandos básicos Docker

### Containers
Listar los containers en ejecución
```
docker ps
```

Listar todos los containers ejecutándose y terminados
```
docker ps -a
```

Mostrar uso de cpu, memoria, etc. de los containers en ejecución
```
docker stats --all
```

Ejecutar una shell en mycontainer (para salir de la shell se usa comando: exit)
```
docker exec -it mycontainer /bin/sh
```

Borrar mycontainer
```
docker rm mycontainer
```

Iniciar un contenedor
```
docker start mycontainer
```

Terminar un contenedor
```
docker stop mycontainer
```

Crear el contenedor a partir de una imagen e iniciarlo
```
docker run [opciones] imagen:version_imagen
```

### Imágenes
Listar las imágenes disponibles para crear contenedores
```
docker images
```

Borrar myimage de las imágenes
```
docker rmi myimage
```

### Descargar imágenes

https://hub.docker.com/

Buscar imagen con el buscador
Ver en pestaña Tag distintas versiones (que tienen distintos tamaños)

ej:
           IMAGEN:TAG 
docker pull nginx:1.13-alpine

### Ejemplos nginx-proxy

```
docker run -d \
  --name nginx-proxy \
  -p 80:80 \
  -v /var/run/docker.sock:/tmp/docker.sock:ro jwilder/nginx-proxy:alpine
```
```
docker run -d \
  --name clientes.frontdev.info \
  -v /var/www/clientes:/usr/share/nginx/html \
  -e VIRTUAL_HOST=clientes.frontdev.info nginx:1.12-alpine
```
```
docker run -d \
  --name blog.frontdev.info \
  -v /var/www/blog:/usr/share/nginx/html \
  -e VIRTUAL_HOST=blog.frontdev.info nginx:1.12-alpine
```
```
docker run -d \
  --name www.frontdev.info \
  -v /var/www/www:/usr/share/nginx/html \
  -e VIRTUAL_HOST=www.frontdev.info nginx:1.12-alpine
```
