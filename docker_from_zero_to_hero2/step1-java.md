Vamos a compilar y ejecutar una aplicación spring-boot con la imagen de maven 3.6.1 con jdk 8 [maven:3.6.1-jdk-8](https://hub.docker.com/_/maven/) para lo cual utilizaemos un Dockerfile

Con `FROM` definiremos nuestra imagen base
<pre class="file" data-filename="Dockerfile" data-target="replace">
FROM maven:3.6.1-jdk-8
</pre>

El comando `RUN` nos permite ejecutar comandos en nuestra imagen base
<pre class="file" data-filename="Dockerfile" data-target="append">
RUN git clone https://github.com/kaox/spring-petclinic.git
</pre>

Con `WORKDIR` vamos a especificar la ruta de trabajo
<pre class="file" data-filename="Dockerfile" data-target="append">
WORKDIR /spring-petclinic/
</pre>

Con `CMD` nos permite ejecutar una acción por defecto cuando inicia el contenedor
<pre class="file" data-filename="Dockerfile" data-target="append">
CMD mvn clean spring-boot:run
</pre>

Para compilar nuestro Dockerfile y convertirla en una imagen ejecutamos `docker image build -t spring-pet .`{{execute}}

Ahora ejecutamos nuestro contenedor exponiendo el puerto 8080 del contenedor y lo mapeamos con el puerto 80 de nuestro host
`docker container run -d -p 80:8080 spring-pet`{{execute}}
