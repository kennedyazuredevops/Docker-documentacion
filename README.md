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

REDES
======


docker network create my-network
docker network ls
docker inspect my-network


docker create -v /var/lib/postgresql/data --name PostgresDataDocker alpine

docker run --name postgresdocker -e POSTGRES_PASSWORD=postgres -d --net=my-network --volumes-from PostgresDataDocker postgres

docker run -it --name ubuntudocker -p 8069:8069 --net=my-network ubuntu:18.04
	root@2e8a4b1e3842:/# apt-get update
	root@2e8a4b1e3842:/# apt-get install iputils-ping
	root@2e8a4b1e3842:/# ping postgresdocker


VOLUMENES
=========

docker run -it --name ubuntudocker -v D:\DOCKER\docker\:/home/ ubuntu:18.04


PUERTOS Y VARIABLES
===================

docker run --name postgres-docker -e POSTGRES_PASSWORD=Aforo255#2019   -d -p 5438:5432  postgres



DOCKER COMPOSE

docker-compose -f .\docker-compose-test.yml up -d
docker-compose -f .\docker-compose-fabio.yml down




NOTA: Para eliminar todos los contenedores de docker

docker rm -f $(docker ps -a -q)

##### Portainer io##########
$ docker volume create portainer_data
$ docker run -d -p 8000:8000 -p 9000:9000 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer

