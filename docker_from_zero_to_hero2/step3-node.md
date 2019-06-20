Vamos a ver un ejemplo de Integración continua con Node, Docker & Bitbucket Pipeline

Clonemos el siguiente [repositorio](https://bitbucket.org/kaoxito/ci-node/src/master/)

`git clone -b develop https://kaoxito@bitbucket.org/kaoxito/ci-node.git`{{execute}}

Cambiamos el repositorio por el que crearon con el comando `git remote set-url origin` y verificamos con `git remote -v`{{execute}}

Creamos nuestro archivo Dockerfile con el siguiente contenido

```
FROM node:11

WORKDIR /app

COPY package.json .

RUN npm install --quiet

COPY . .

EXPOSE 3000

CMD ["npm", "start"]
```

Luego compilamos nuestra imagen `docker build -t node-app .`{{execute}} y la ejecutamos `docker run -d -p 80:3000 node-app`{{execute}}

Probamos nuestro servicio http://URL/persona/ruc/ http://URL/persona/dni/

Ahora creamos el archivo bitbucket-pipelines.yml con el siguiente contenido

```

image: atlassian/default-image:2

pipelines:
  branches:
    master:
      - step:
          name: "Build & Publish Docker Image"
          services:
            - docker
          script:
            - export IMAGE_NAME=kaox/taller-ninja-node
            - docker build -t $IMAGE_NAME .
            - docker login --username $DOCKER_HUB_USERNAME --password $DOCKER_HUB_PASSWORD
            - docker push $IMAGE_NAME
definitions:
  services:
    docker:
      memory: 2048

```