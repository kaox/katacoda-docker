Con el comando `docker container` administraremos los contenedores de Docker, para ver todas las opciones que tenemos vamos a ejecutar la ayuda del comando

`docker container --help`{{execute}}

### ls
Con el comando `docker container ls` listaremos los contenedores en ejecución

`docker container ls`{{execute}}

Para mostrar todos los contenedores (en ejecución y detenidas) ejecutar `docker container ls -a`{{execute}}

### run
Con el comando `docker container run [image]` creamos un nuevo contenedor desde una imagen y se ejecuta

`docker container run hello-world`{{execute}}

Para acceder a la terminal de un contenedor ejecutamos `docker run -it ubuntu bash`{{execute}} , para salir del contenedor y regresar a nuestro host ejecutamos `exit`{{execute}}