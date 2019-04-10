Con el comando `docker image` administraremos las imagenes de Docker, para ver todas las opciones que tenemos vamos a ejecutar la ayuda del comando

`docker image --help`{{execute}}

### pull
Con el comando `docker image pull [image]` descargaremos la imagenes del registry (Docker Hub), en modo de ejemplo descargaremos dos imagenes una de ubuntu y otra de tomcat.

`docker image pull ubuntu`{{execute}}

`docker image pull tomcat:8.5-alpine`{{execute}}

### ls
Para ver las imagenes que hemos descargado ejecutamos el comando `docker image ls`{{execute}}

### rm
Para eliminar las imagenes usamos el comando `docker image rm [image]`

`docker image rm ubuntu`{{execute}}

Listamos nuestras imagenes para ver que se eliminó correctamente `docker image ls`{{execute}}

### inspect
Para ver el información detallada de imagenes usaremos el comando `docker inspect [image]`

`docker image inspect tomcat:8.5-alpine`{{execute}}

### tag
Con el comando `docker image tag [image_base] [image_tag]` vamos a crear un nueva imagen con un nombre distinto a partir de una imagen base.

`docker tag tomcat:8.5-alpine kaox/webapp`{{execute}}

Listamos nuestras imagenes para ver la imagen nueva que se creo `docker image ls`{{execute}}

### push
Con el comando `docker image push [image_tag]` enviamos nuestra imagen al registry (Docker Hub)

Para poder enviar la imagen necesitamos estar logueados en docker con nuestras credenciales del Docker Hub

`docker login`{{execute}}

Una vez logueados ya podriamos enviar nuestra imagen al registry, para que se envie la imagen tenemos que tagear nuestra imagen con nuestro id, en mi caso mi id es kaox es por eso que le puse el nombre de kaox/webapp, ustedes tendran que usar su id para enviar la imagen.

`docker push kaox/webapp`{{execute}}

### prune
Con el comando `docker image prune`{{execute}} limpiaremos nuestras imagenes colgadas.