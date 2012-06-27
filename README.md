# Clase-de-github - en la rama mejorandola
==========================================

Este es un ejemplo de Github para la comunidad de #mejorandola
Suscribete en nuestro canal de [YouTube](http://www.youtube.com/mejorandolaweb) y mira el [video](http://mejorando.la/videos/curso-de-introduccion-git-y-github/) de la clase de github.

Nota: este archivo fué modificado, le agregamos unas cuantas descripciones para entender mejor lo que se hizo en el curso.
mira el archivo original viendo su [historial](https://github.com/Mejorandola/clase-de-github/commits/master/README.md)

listo, empecemos:

## Instalar GIT
  puedes ver la [documentación](https://help.github.com/articles/set-up-git#platform-all) de GitHub para instalar git.

  Una vez instalas GIT en tu computadora, debes configurarlo desde tu consola:

    git config --global user.name "Christian"
    git config --global user.email "xxxxxx@xxxx.com"

## Generando tu Public Key:
  Se necesita una llave SSH para conectar tu maquina local con el repositorio remoto de GitHub.
  en consola:
  
    ssh-keygen

  esto generará una llave con la cual te conectarás a GitHub.
  
  Leyendo tu llave para copiarla a Github de nuevo a la consola:
  
    cat ~/.ssh/id_rsa.pub
  
  * copia y pega el contenido que te da cat, o puedes usar cualquier editor para copiar el contenido de la llave a tu portapapeles.
  * Ahora debes copiar ese contenido (tu llave) en '[github ssh](https://github.com/settings/ssh)' tal cual como lo tienes.
  
y listo! ya tenemos listas las herramientas para la conexión entre nuestra computadora y GitHub

## Arrancando tu proyecto:
  En local debes inicializar tu proyecto con git:
  
    git init

    touch README

    git add README

    git commit -m "tu primer commit"
    
## Creando la conexión remota a GitHub:
  Para subir tu commit a github debemos crear una conexión remota, aquí usaremos nuestra llave SSH.
  Crearemos un alias para nuestra conexión y le asignaremos un nombre, en este caso 'origin':
    
    git remote add origin git@github.com:USUARIO/NOMBRE-DE-MI-REPO.git
  
  Nota: El alias origin es el mas usado, pero puedes poner el nombre que quieras. Recuerda cambiar tu nombre de USUARIO y el NOMBRE-DE-MI-REPO.
  
  Datos importantes:
  * En 'origin' quedó guardado el destino del repositorio al cual queremos subir nuestros commitis, y ya nunca mas debemos ejecutar la linea anterior en nuestro proyecto.
  * Debes crear un alias para cada proyecto
  * Puedes crear varias conexiones remotas para el mismo proyecto, ejemplo: `git remote add myapp git@github.com:USUARIO/NOMBRE-DE-MI-OTRO-REPO.git` 
  * No solo puedes crear conexiones remotas hacia Github, sino también a cualquier servidor que tenga instalado Git, ej: heroku
  
  #### Consultar alias
  Para consultar cuales son las conexiones que tenemos en nuestro proyecto o para verificar que tenemos una:
  
    `git remote`
  
  aqui se listaran nuestras conexiones, en nuestro caso: `origin`
  
## Enviando todo nuestro commit a GitHub
  Una vez tengamos una versión de nuestro código (commit) en local, y tengamos nuestra conexión remota a nuestro repo en github:

    git push origin master

  Nos pedirá la contraseña que pusimos al crear la llave SSH y LISTO! Ya tenemos nuestro código en GitHub
  
  NOTA: recuerda poner la url "git@github.com:USUAR....." de SSH, si pones "https://github.com/USUAR..." osea el acceso por HTTP, siempre que hagas un commit te pedirá nombre de usuario de GitHub y tu Contraseña.

Descripciones y detalles por [@MaoAiz](https://twitter.com/#!/MaoAiz)


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