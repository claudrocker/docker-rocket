# docker-rocket
Lista de comandos Docker más usados

## Instalar docker

Para debian jessie: https://docs.docker.com/engine/installation/linux/debian/

$ apt-get install \
     apt-transport-https \
     ca-certificates \
     curl \
     gnupg2 \
     software-properties-common

$ curl -fsSL https://download.docker.com/linux/debian/gpg | apt-key add -

add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/debian \
   $(lsb_release -cs) \
   stable"

apt-get update

apt-get install docker-ce

verificar con: 
docker --version
