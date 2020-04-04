"# Docker-documentacion" 


Hoja de resumen y trampa
## List Docker CLI commands
docker
docker container --help

## Display Docker version and info
docker --version
docker version
docker info

## Execute Docker image
docker run hello-world

## List Docker images
docker image ls

## List Docker containers (running, all, all in quiet mode)
docker container ls
docker container ls --all
docker container ls -aq


## eliminar un contenedor
docker rm <nombreContendedo>
*se puede poder las 3 primeras letras del contenedorID
## eliminar 


## listar los contenedores corriendo
docker ps -a


## ejecutar una imagen en un contenedor con puerto
docker run -p 4000:80 hello-world


## correr liferay docker
7.2.10
7.0.10.11-201906281450

docker run -it -p 8080:8080 liferay/dxp:7.2.10 /bin/sh

docker run --name LIFERAY_DXP_7.2.10 -p 8080:8080 liferay/dxp:7.2.10-dxp-4

docker run --name LIFERAY_DXP_7.0.10 -p 8080:8080 liferay/dxp:7.0.10.11-201906281450

*si sale un error d tty, probar con el power shell


## para inspeccionar docker
docker inspect <nombre_image>


### escuchan un puerto
netstat -ap|grep http



## para ingresar al contenedor como usuario admin
docker exec -u 0 -it <NOMBRE_CONTEDOR/ID> bash

## para ingresar al contenedor como usuario defecto
docker exec -it <NOMBRE_CONTEDOR/ID> bash

### Salir del vi
:q ---> cuando no se han hecho notificaciones
:q!---> salir y descartar los cambios
:wq---> salir y guardar los cambios


## Link de liferay  docker
https://hub.docker.com/r/liferay/dxp/tags


## iniciar contenedor
docker start <NOMBRE_CONTEDOR/ID>

## detener contenedor
docker stop <NOMBRE_CONTEDOR/ID>


###para inciar jenkis

sudo systemctl start jenkins

###Listar las redes

docker network ls

### verifica la ip del contenedor
docker inspect -f ' { {range.NetworkSettings.Networks } } { { .IPAddress } } { { end } } ' 092d7808fec2


###ip del contenedor
docker inspect -f "{{.NetworkSettings.IPAddress}}" app_nginx

docker-machine ls
