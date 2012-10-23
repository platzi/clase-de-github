clase-de-github - en la rama mejorandola 
===============

Este es un ejemplo de Github para la comunidad de #mejorandola 

Una vez instalas GIT, debes configurarlo:

git config --global user.name "Christian"
git config --global user.email "xxxxxx@xxxx.com"

Generando tu Public Key:

ssh-keygen 

Leyendo tu llave para copiarla a Github:

cat ~/.ssh/id_rsa.pub

Arrancando tu proyecto:

git init

touch README

git add README

git commit -m "tu primer commit"

git push origin master

/************************************GIT desde 0 - Por @klinsmannf****************************************/

<h3>configuración</h3>
Descarga git para OSX

Descarga git para Windows

Descarga git para Linux

<h3>crea un repositorio nuevo</h3>
crea un directorio nuevo, ábrelo y ejecuta
git init
para crear un repositorio de git nuevo.

<h3>hacer checkout a un repositorio</h3>
crea una copia local del repositorio ejecutando
git clone /path/to/repository
al utilizar un servidor remoto, el comando será
git clone username@host:/path/to/repository

<h3>flujo de trabajo</h3>
tu repositorio local esta compuesto por tres "árboles" administrados por git. el primero es tu Directorio de trabajo el cual contiene los archivos. el segundo es el Index el cual actua como un área intermedia y finalmente el HEAD el cual apunta a el último commit realizado.


<h3>add & commit</h3>
Puedes proponer cambios (agregarlos a el Index) usando
git add <filename>
git add *
Este es el primer paso en el flujo de trabajo básico. Para en realidad hacer commit a estos cambios usa
git commit -m "Commit message"
Ahora el archivo esta incluído en el HEAD, pero aún no en tu repositorio remoto.

<h3>envío de cambios</h3>
Tus cambios están ahora en el HEAD de tu copia local. Para enviar esos cambios a tu repositorio remoto ejecuta 
git push origin master
Reemplaza master por la rama a la cual desees enviar tus cambios. 

Si no has clonado un repositorio existente y quieres conectar tu repositorio a un repositorio remoto, necesitas agregarlo con
git remote add origin <server>
Ahora puede subir tus cambios al repositorio remoto selecionado
ramas
Las ramas son utilizadas para desarrollar funcionalidades aisladas unas de otras. La rama master es la rama por "defecto" cuando creas un repositorio. Usa otras ramas para el desarrollo y fusionalas de regreso a la rama principal al terminar.


<h3>crea una nueva rama llamada "feature_x" y cambiate a ella usando:</h3>
git checkout -b feature_x
regresa a la rama principal
git checkout master
y borra la rama
git branch -d feature_x
una rama no está disponible para los demás a menos que subas (push) la rama a tu repositorio remoto
git push origin <branch>

<h3>actualiza & fusiona</h3>
para actualizar tu repositorio local al commit más nuevo, ejecuta 
git pull
en tu directorio de trabajo fetch y merge cambios remotos.
para fusionar otra rama a tu rama activa (por ejemplo master), utiliza
git merge <branch>
en ambos casos git intenta auto fusionar cambios. Desafortunadamente, esto no es posible todo el tiempo y resulta en conflictos. Tú eres responsable de fusionar esos conflictos manualmente al editar los archivos mostrados por git. Luego de modificarlos, necesitas marcarlos como fusionados con
git add <filename>
antes de fusionar cambios, también puedes dar un vistazo previo usando
git diff <source_branch> <target_branch>

<h3>etiquetas</h3>
es recomendado crear etiquetas para cada versión publicada de un software. esto es un concepto conocido, el cual tambien existe en SVN. Puedes crear una nueva etiqueta llamada 1.0.0 ejecutando
git tag 1.0.0 1b2e1d63ff
el 1b2e1d63ff se refiere a los 10 caracteres de el commit id al cual quieres referirte con tu etiqueta. Puedes obtener el commit id con 
git log
también puedes usar menos caracteres que el commit id, pero debe ser un valor único.

<h3>reemplaza cambios locales</h3>
En caso de que hagas algo malo (que de seguro nunca pasa ;) puedes reemplazar cambios locales usando el comando
git checkout -- <filename>
esto reemplaza los cambios en tu árbol de trabajo con el último contenido de HEAD. Los cambios que ya han sido agregados al índice, así como también nuevos archivos, se mantendrán sin cambio.

Si por otro lado quieres deshacerte de todos los cambios locales y commits, puedes traer la última versión del servidor y apuntar a tu copia local principal de esta forma
git fetch origin
git reset --hard origin/master

<h3>datos útiles</h3>
Interfaz gráfica por defecto
gitk
colores especiales para la consola
git config color.ui true
mostrar sólo una línea por cada commit en la traza
git config format.pretty oneline
agregar archivos de forma interactiva
git add -i

<h3>enlaces & recursos</h3>
clientes gráficos
GitX (L) (OSX, open source)
Tower (OSX)
Source Tree (OSX, free)
GitHub for Mac (OSX, free)
guías
Git Community Book
Pro Git
Think like a git
GitHub Help
A Visual Git Guide