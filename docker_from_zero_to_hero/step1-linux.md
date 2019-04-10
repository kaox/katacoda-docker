### pwd
Pwd (print working directory) nos muestra la ruta en donde nos encontramos

`pwd`{{execute}}

### mkdir
Mkdir (Make directory) crea carpetas nuevas

`mkdir taller-ninja`{{execute}}

Si queremos crear una carpeta oculta anteponemos un punto en el nombre de la carpeta

`mkdir .ninja-oculto`{{execute}}

Para crear un arbol de carpetas usamos la opción -p y para crear varias carpetas en un mismo nodo usamos `{sub1,sub2}` 

`mkdir -p taller-ninja/{carpeta1,carpeta2/{sub1,sub2},carpeta3}`{{execute}}

### touch
Crea archivos vacios 

`touch cinturon-negro.txt`{{execute}}

Tambien podemos crear varios archivos en diferentes carpetas

`touch taller-ninja/carpeta1/cinturon-marron.txt taller-ninja/carpeta2/cinturon-azul.txt`{{execute}}

### ls
Lista el contenido de un directorio

`ls`{{execute}}

`ls taller-ninja/carpeta1/`{{execute}}

Para ver los archivos y carpetas ocultas utilizamos la opción `-a`

`ls -a`{{execute}}

Para ver los archivos y carpetas de forma recursiva utilizamos la opción `-R`

`ls -Ra`{{execute}}

### apt
Apt (Advanced Packaging Tool) nos permite instalar, actualizar o eliminar aplicaciones

Para sincronizar las fuentes de los paquetes usamos 

`apt update`{{execute}}

Para actualizar todos los paquetes a la ultima versión usamos `apt upgrade` para este taller no es necesario ejecutarlo.

Para instalar un paquete usamos la opción `install`

`apt install tree`{{execute}}

### cd
Cd (Change Directory) nos permite movernos entre directorios

`cd taller-ninja/carpeta1/`{{execute}}

Y si queremos subir de nivel (es decir retroceder una carpeta) utilizamos el comando`cd ../`

### cp
Cp (Copy) nos permite copiar archivos o directorios

`cp taller-ninja/carpeta1/cinturon-marron.txt taller-ninja/carpeta2/cinturon-marron.txt`{{execute}}

Para copiar el contenido de un directorio de forma recursiva utilizamos la opción `-r` 

`cp -r taller-ninja/carpeta2/ taller-ninja/carpeta3/`{{execute}}

### mv
Mv (Move) nos permite mover archivos o directorios

`mv cinturon-negro.txt taller-ninja/carpeta3/`{{execute}}

### rm
Rm (Remove) nos sirve para eliminar un archivo o directorio, para borrar un archivo usamos el comando `rm taller-ninja/carpeta3/cinturon-negro.txt`{{execute}}

Para borrar una carpeta de forma recursiva utilizar la opción `-r`, la opción `-f` sirve para no pedir confirmación y forzar el borrado.

`rm -rf taller-ninja/`{{execute}}

### cat
Nos permite ver el contenido de un archivo

`cat /etc/hosts`{{execute}}