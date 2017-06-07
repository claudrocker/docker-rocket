# docker-rocket
Lista de comandos Docker más usados

## Instalar docker
Para debian jessie: https://docs.docker.com/engine/installation/linux/debian/

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
