Para este taller vamos a trabajar con una aplicación Java con JSF, los pasos para desplegar esta aplicación son los siguientes:

* Compilar proyecto.
* Desplegar war en Apache Tomcat.

### Compilar proyecto

Vamos a compilar la aplicación con maven 3.6.1 con jdk 11, para lo cual nos bajamos la imagen `docker image pull maven:3.6.1-jdk-11`{{execute}}

La ejecutamos compartiendo un volumen en nuestro host con el container `docker container run -it -v /root:/root maven:3.6.1-jdk-11 bash`{{execute}}

Ahora estamos dentro del container y descargaremos el codigo fuente de la aplicacion en el container `git clone https://github.com/kaox/project-java-jsf-webapp.git`{{execute}}

