Vamos a compilar la aplicación java jsf con la imagen de maven 3.6.1 con jdk 8 [maven:3.6.1-jdk-8](https://hub.docker.com/_/maven/) y luego lo desplegaremos en un tomcat [tomcat:8.5.42-jdk8-openjdk](https://hub.docker.com/_/tomcat) para lo cual utilizaemos un Dockerfile

Con `FROM` definiremos nuestra imagen base maven:3.6.1-jdk-8
<pre class="file" data-filename="Dockerfile" data-target="replace">
FROM maven:3.6.1-jdk-8 as maven
</pre>

Definimos el `WORKDIR` /app/
<pre class="file" data-filename="Dockerfile" data-target="append">
WORKDIR /app/
</pre>

Con el comando `RUN` clonaremos el repositorio del aplicativo y luego lo empaquetamos con maven
<pre class="file" data-filename="Dockerfile" data-target="append">
RUN git clone https://github.com/kaox/project-java-jsf-webapp.git && \
mvn package -f project-java-jsf-webapp/pom.xml
</pre>

Definimos como nueva imagen base a tomcat:8.5.42-jdk8-openjdk
<pre class="file" data-filename="Dockerfile" data-target="append">
FROM tomcat:8.5.42-jdk8-openjdk
</pre>

Eliminamos la carpeta /usr/local/tomcat/webapps/ROOT de la imagen
<pre class="file" data-filename="Dockerfile" data-target="append">
RUN rm -rf /usr/local/tomcat/webapps/ROOT
</pre>

Con el comando `COPY` copiamos el WAR desde nuestra imagen maven hacia la imagen de tomcat
<pre class="file" data-filename="Dockerfile" data-target="append">
COPY --from=maven /app/project-java-jsf-webapp/target/*.war $CATALINA_HOME/webapps/
</pre>

Para compilar nuestro Dockerfile y convertirla en una imagen ejecutamos `docker image build -t tomcat-app .`{{execute}}

Ahora ejecutamos nuestro contenedor exponiendo el puerto 8080 del contenedor y lo mapeamos con el puerto 80 de nuestro host
`docker container run -d -p 80:8080 tomcat-app`{{execute}}
