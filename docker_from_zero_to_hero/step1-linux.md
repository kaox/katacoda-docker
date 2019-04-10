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

### cd
Cd (Change Directory) nos permite movernos entre directorios

`cd taller-ninja/carpeta1/`{{execute}}

Y si queremos subir de nivel (es decir retroceder una carpeta)

`cd ../`{{execute}}

### cp
Cp (Copy) nos permite copiar archivos o directorios

`cp taller-ninja/carpeta1/cinturon-marron.txt taller-ninja/carpeta2/cinturon-marron.txt`{{execute}}

Para copiar el contenido de un directorio de forma recursiva utilizamos la opción `-r` 

`cp -r taller-ninja/carpeta2/ taller-ninja/carpeta3/`{{execute}}

### mv
Mv (Move) nos permite mover archivos o directorios

`mv cinturon-negro.txt taller-ninja/carpeta3/`{{execute}}

### rm
Rm (Remove) Elimina 


### cat



### apt
