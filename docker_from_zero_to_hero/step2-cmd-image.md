Con el comando `docker image` administraremos las imagenes de Docker, para ver todas las opciones que tenemos vamos a ejecutar la ayuda del comando

`docker image --help`{{execute}}

#### pull
Con el comando `docker image pull [image]` descargaremos la imagenes del registry (Docker Hub), en modo de ejemplo descargaremos dos imagenes una de ubuntu y otra de tomcat.

`docker image pull ubuntu`{{execute}}

`docker image pull tomcat:8.5-alpine`{{execute}}

#### ls
Para ver las imagenes que hemos descargado ejecutamos el comando `docker image ls`{{execute}}

#### rm
Para eliminar las imagenes usamos el comando `docker image rm [image]`

`docker image rm ubuntu`{{execute}}

Listamos nuestras imagenes para ver que se eliminó correctamente `docker image ls`{{execute}}

#### inspect
Para ver el información detallada de imagenes usaremos el comando `docker inspect [image]`

`docker image inspect tomcat:8.5-alpine`{{execute}}

#### tag
Etiquetamos una imagen
`docker tag tomcat:8.5-alpine kaox/webapp`{{execute}}
`docker image ls`{{execute}}

#### push
Enviamos una imagen al registry
`docker login`{{execute}}
`docker push kaox/webapp`{{execute}}

#### prune
Limpiamos las imagenes colgadas
`docker image prune`{{execute}}