Con el comando `docker image` administraremos las imagenes de Docker, para ver todas las opciones que tenemos vamos a ejecutar la ayuda del comando

`docker image --help`{{execute}}

#### pull
Descargar las imagenes del registry (Docker Hub) 
`docker image pull ubuntu`{{execute}}
`docker image pull tomcat:8.5-alpine`{{execute}}

#### ls
Lista las imagenes
`docker image ls`{{execute}}

#### rm
Elimina imagenes
`docker image rm ubuntu`{{execute}}
`docker image ls`{{execute}}

#### inspect
Mustra el detalle de la imagen
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