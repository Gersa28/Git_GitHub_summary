# Git y GitHub

# 1_¿Por qué usar un sistema de control de versiones como Git?

Un sistema de control de versiones como Git nos ayuda a guardar el historial de cambios y crecimiento de los archivos de nuestro proyecto.

En realidad, los cambios y diferencias entre las versiones de nuestros proyectos pueden tener similitudes, algunas veces los cambios pueden ser solo una palabra o una parte específica de un archivo específico. Git está optimizado para guardar todos estos cambios de forma atómica e incremental, o sea, aplicando cambios sobre los últimos cambios, estos sobre los cambios anteriores y así hasta el inicio de nuestro proyecto.

El comando para iniciar nuestro repositorio, o sea, indicarle a Git que queremos usar su sistema de control de versiones en nuestro proyecto, es git init.

El comando para que nuestro repositorio sepa de la existencia de un archivo o sus últimos cambios es git add. Este comando no almacena las actualizaciones de forma definitiva, únicamente las guarda en algo que conocemos como “Staging Area” (área de montaje o ensayo).

El comando para almacenar definitivamente todos los cambios que por ahora viven en el staging area es git commit. También podemos guardar un mensaje para recordar muy bien qué cambios hicimos en este commit con el argumento -m "Mensaje del commit".

Por último, si queremos mandar nuestros commits a un servidor remoto, un lugar donde todos podamos conectar nuestros proyectos, usamos el comando git push.

Comandos básicos de git

git init: inicializa un repositorio de GIT en la carpeta donde se ejecute el comando.

git add: añade los archivos especificados al área de preparación (staging).

git commit -m “commit description”: confirma los archivos que se encuentran en el área de preparación y los agrega al repositorio.

git commit -am “commit description”: añade al staging area y hace un commit mediante un solo co demando. (No funciona con archivos nuevos)

git status: ofrece una descripción del estado de los archivos (untracked, ready to commit, nothing to commit).

git rm (. -r, filename) (–cached): remueve los archivos del index.

git config --global user.email tu@email.com: configura un email.

git config --global user.name <Nombre como se verá en los commits>: configura un nombre.

git config --list: lista las configuraciones.

Analizar cambios en los archivos de un proyecto Git

git log: lista de manera descendente los commits realizados.

git log --stat: además de listar los commits, muestra la cantidad de bytes añadidos y eliminados en cada uno de los archivos modificados.

git log --all --graph --decorate --oneline: muestra de manera comprimida toda la historia del repositorio de manera gráfica y embellecida.

git show filename: permite ver la historia de los cambios en un archivo.

git diff `<commit1>` `<commit2>`: compara diferencias entre en cambios confirmados.

Volver en el tiempo con branches y checkout

git reset `<commit>` --soft/hard: regresa al commit especificado, eliminando todos los cambios que se hicieron después de ese commit.

git checkout <commit/branch> `<filename>`: permite regresar al estado en el cual se realizó un commit o branch especificado, pero no elimina lo que está en el staging area.

git checkout – `<filePath>`: deshacer cambios en un archivo en estado modified (que ni fue agregado a staging)

git rm y git reset

git rm:

Este comando nos ayuda a eliminar archivos de Git sin eliminar su historial del sistema de versiones. Esto quiere decir que si necesitamos recuperar el archivo solo debemos “viajar en el tiempo” y recuperar el último commit antes de borrar el archivo en cuestión.

git rm no puede usarse por sí solo, así nomás. Se debe utilizar uno de los flags para indicar a Git cómo eliminar los archivos que ya no se necesitan en la última versión del proyecto:

git rm --cached <archivo/s>: elimina los archivos del área de Staging y del próximo commit, pero los mantiene en nuestro disco duro.

git rm --force <archivo/s>: elimina los archivos de Git y del disco duro. Git siempre guarda todo, por lo que podemos acceder al registro de la existencia de los archivos, de modo que podremos recuperarlos si es necesario (pero debemos aplicar comandos más avanzados).

git reset

Con git reset volvemos al pasado sin la posibilidad de volver al futuro. Borramos la historia y la debemos sobreescribir.

git reset --soft: Vuelve el branch al estado del commit especificado, manteniendo los archivos en el directorio de trabajo y lo que haya en staging considerando todo como nuevos cambios. Así podemos aplicar las últimas actualizaciones a un nuevo commit.

git reset --hard: Borra absolutamente todo. Toda la información de los commits y del área de staging se borra del historial.

git reset HEAD: No borra los archivos ni sus modificaciones, solo los saca del área de staging, de forma que los últimos cambios de estos archivos no se envíen al último commit. Si se cambia de opinión se los puede incluir nuevamente con git add.

Ramas o Branches en git

Al crear una nueva rama se copia el último commit en esta nueva rama. Todos los cambios hechos en esta rama no se reflejarán en la rama master hasta que hagamos un merge.

git branch `<new branch>`: crea una nueva rama.

git checkout `<branch name>`: se mueve a la rama especificada.

git merge `<branch name>`: fusiona la rama actual con la rama especificada y produce un nuevo commit de esta fusión.

git branch: lista las ramas generadas.

Aporte creado por: Franco Coloccini

# 2_ ¿Qué es Git?

Git es un sistema de control de versiones distribuido, diseñado por Linus Torvalds. Está pensando en la eficiencia y la confiabilidad del mantenimiento de versiones de aplicaciones cuando estas tienen un gran número de archivos de código fuente. Git está optimizado para guardar todos estos cambios de forma atómica e incremental.

Se obtiene su mayor eficiencia con archivos de texto plano, ya que con archivos binarios no puede guardar solo los cambios, sino que debe volver a grabar el archivo completo ante cada modificación, por mínima que sea, lo que hace que incremente demasiado el tamaño del repositorio.

“Guardar archivos binarios en el repositorio de git es una mala práctica, únicamente deberían guardarse archivos pequeños (como logos) que no sufran casi modificaciones durante la vida del proyecto. Los binarios deben guardarse en un CDN”.

¿Qué es un sistema de control de versiones?

El SCV o VCS (por sus siglas en inglés) es un sistema que registra los cambios realizados sobre un archivo o conjunto de archivos a lo largo del tiempo, de modo que puedas llevar el historial del ciclo de vida de un proyecto, comparar cambios a lo largo del tiempo, ver quién los realizó o revertir el proyecto entero a un estado anterior.

Cualquier tipo de archivo que se encuentre en un ordenador puede ponerse bajo control de versiones.

¿Qué es Github?

Es una plataforma de desarrollo colaborativo para alojar proyectos utilizando el sistema de control de versiones Git. Se emplea principalmente para la creación de código fuente de programas de computadora.

Github puede considerarse como la red social de código para los programadores y en muchos casos es visto como tu curriculum vitae, pues aquí guardas tu portafolio de proyectos de programación.

## VIDEO:

[https://www.youtube.com/watch?v=DinilgacaWs](https://www.youtube.com/watch?v=DinilgacaWs)

# 6_Editores de código, archivos binarios y de texto plano

# **7 Introducción a la terminal y línea de comandos**

MARCADORES
La línea de comandos nos permite interactuar con nuestro computador sin necesidad de utilizar una interfaz gráfica. Sin embargo, los computadores emplean distintos sistemas de archivos y manejan diferentes comandos, dependiendo del sistema operativo que utilicen.

Diferencias entre la estructura de archivos de Windows, Mac o Linux.
La ruta principal en Windows es C:\, en UNIX es solo /.
Windows no hace diferencia entre mayúsculas y minúsculas pero UNIX sí.
Recuerda que GitBash usa la ruta /c para dirigirse a C:\ (o /d para dirigirse a D:\) en Windows. Por lo tanto, la ruta del usuario con el que estás trabajando es /c/Users/Nombre de tu usuario

Comandos básicos en la terminal:
pwd: Nos muestra la ruta de carpetas en la que te encuentras ahora mismo.
mkdir: Nos permite crear carpetas (por ejemplo, mkdir Carpeta-Importante).
touch: Nos permite crear archivos (por ejemplo, touch archivo.txt).
rm: Nos permite borrar un archivo o carpeta (por ejemplo, rm archivo.txt). Mucho cuidado con este comando, puedes borrar todo tu disco duro.
cat: Ver el contenido de un archivo (por ejemplo, cat nombre-archivo.txt).
ls: Nos permite cambiar ver los archivos de la carpeta donde estamos ahora mismo. Podemos usar uno o más argumentos para ver más información sobre estos archivos (los argumentos pueden ser -- + el nombre del argumento o - + una sola letra o shortcut por cada argumento).

- ls -a: Mostrar todos los archivos, incluso los ocultos.
- ls -l: Ver todos los archivos como una lista.
  cd: Nos permite navegar entre carpetas.
- cd /: Ir a la ruta principal:
- cd o cd ~: Ir a la ruta de tu usuario
- cd carpeta/subcarpeta: Navegar a una ruta dentro de la carpeta donde estamos ahora mismo.
- cd .. (cd + dos puntos): Regresar una carpeta hacia atrás.
- Si quieres referirte al directorio en el que te encuentras ahora mismo puedes usar cd . (cd + un punto).
  history: Ver los últimos comandos que ejecutamos y un número especial con el que podemos repetir su ejecución.
  ! + número: Ejecutar algún comando con el número que nos muestra el comando history (por ejemplo, !72).
  clear: Para limpiar la terminal. También podemos usar los atajos de teclado Ctrl + L o Command + L.
  Todos estos comandos tiene una función de autocompletado, o sea, puedes escribir la primera parte y presionar la tecla Tab para que la terminal nos muestre todas las posibles carpetas o comandos que podemos ejecutar. Si presionas la tecla Arriba puedes ver el último comando que ejecutamos.

Recuerda que podemos descubrir todos los argumentos de un comando con el argumento --help (por ejemplo, cat --help).

Aporte creado por: Diego Camacho

Comandos Principales

pwd nos muestra el path o ruta de la carpeta en donde nos encontramos ubicados
cd me permite acceder (entrar) a una carpeta en un nivel o varios niveles
cd .. me permite salir de una carpeta en un nivel o varios niveles OJO los dos puntos deben ser separados por un espacio del comando cd
ls me muestra los archivos que contiene una carpeta, puede ser la ubicación actual o una ruta especifica, no muestra los archivos ocultos
ls -a me muestra los archivos que contiene una carpeta, puede ser la ubicación actual o una ruta especifica, incluyendo los archivos ocultos
ls -l me lista los archivos que contiene una carpeta con sus atributos, puede ser la ubicación actual o una ruta especifica, no muestra los archivos ocultos
ls -la me lista los archivos que contiene una carpeta con sus atributos, puede ser la ubicación actual o una ruta especifica, incluyendo los archivos ocultos
clear limpiar la consola o terminal, o un shorcut crtl + L
mkdir `<nombre carpeta>` nos permite crear una carpeta
touch `<nombre del archivo>` nos permite crear un archivo
cat `<nombre del archivo>` me permite visualizar el contenido del un archivo y lo muestra en el terminal
history nos muestra un historial de los comandos que hemos utilizado
rm `<nombre del archivo>` me permite borrar un archivo
OJO en Windows el terminal no es case sensitive (Sensible las mayusculas), con Linux,y UNIX si son case sensitive

# **8- Crea un repositorio de Git y haz tu primer commit**

No te funciona el comando *code* en tu terminal?

- Abre Visual Studio Code
- Presiona *cmd + shift + p* ó si estás en windows *ctrl + shift + p*
- Busca una opción que diga lo siguiente: *Shell Command: Install 'code' command in $PATH*
- Selecciónala

![Untitled](Git%20y%20GitHub%20a7cd841d61cc4e0bb4d3c27f90bb55c5/Untitled.png)

Le indicaremos a Git que queremos crear un nuevo repositorio para utilizar su sistema de control de versiones. Solo debemos posicionarnos en la carpeta raíz de nuestro proyecto y ejecutar el comando:

```bash
git init

```

Recuerda que al ejecutar este comando (y de aquí en adelante) vamos a tener una nueva carpeta oculta llamada `.git` con toda la base de datos con cambios atómicos en nuestro proyecto.

Recuerda que Git está optimizado para trabajar en equipo, por lo tanto, debemos darle un poco de información sobre nosotros. No debemos hacerlo todas las veces que ejecutamos un comando, basta con ejecutar solo una sola vez los siguientes comandos con tu información:

```bash
git config --global user.email "tu@email.com"
git config --global user.name "Tu Nombre"

```

Existen muchas otras configuraciones de Git que puedes encontrar ejecutando el comando `git config --list` (o solo `git config` para ver una explicación más detallada).

Si quieres ver los archivos ocultos de una carpeta puedes habilitar la opción de `Vista > Mostrar u ocultar > Elementos ocultos` (en Windows) o ejecutar el comando `ls -a`.

## Comandos para iniciar tu repositorio con Git

- git init: para inicializar el repositorio git y el staged
- git add nombre_del_archivo.txt: enviar el archivo al staged
- git status: ver el estado, si se requiere agregar al starget o si se requiere commit
- git conf: para ver las posibles configuraciones
- git conf --list: para ver la lista de configuraciones hechas
- git conf --list --show-origin: para mostrar las configuraciones y sus rutas
- git rm --cached nombre_del_archivo.txt: para eliminar el archivo del staged(ram)
- git rm nombre_del_archivo.txt: para eliminar del repositorio

Si por algún motivo te equivocaste en el nombre o email que configuraste al principio, lo puedes modificar de la siguiente manera:

`git config --global --replace-all user.name “Aquí va tu nombre modificado”`

O si lo deseas eliminar y añadir uno nuevo `git config --global --unset-all user.name :Elimina el nombre del usuariogit config --global --add user.name “Aquí va tu nombre”`

# 9- Analizar cambios en los archivos de tu proyecto con Git

El comando **git show** nos muestra los cambios que han existido sobre un archivo y es muy útil para detectar cuándo se produjeron ciertos cambios, qué se rompió y cómo lo podemos solucionar. Pero podemos ser más detallados.

Si queremos ver la diferencia entre una versión y otra, no necesariamente todos los cambios desde la creación del archivo, podemos usar el comando **git diff commitA commitB**.

Recuerda que puedes obtener el ID de tus commits con el comando **git log**.

## Comandos para analizar cambios en GIT

- **git init**: inicializar el repositorio
- **git add nombre_de_archivo.extensión**: agregar el archivo al repositorio
- **git commit -m “Mensaje”**: Agregamos los cambios para el repositorio
- **git add**: Agregar los cambios de la carpeta en la que nos encontramos agregar todo
- **git log —oneline:** nos muestra la lista de todas las instantaneas que tenemos (muy buena)
- **git status**: visualizar cambios
- **git log nombre_de_archivos.extensión**: histórico de cambios con detalles
- **git push**: envía a otro repositorio remoto lo que estamos haciendo
- **git pull**: traer repositorio remoto
- **ls**: listado de carpetas en donde me encuentro. Es decir, como emplear dir en windows.
- **pwd**: ubicación actual
- **mkdir**: make directory nueva carpeta
- **touch archivo.extensión**: crear archivo vacío
- **cat archivo.extensión**: muestra el contenido del archivo
- **history**: historial de comandos utilizados durante esa sesión
- **rm archivo.extensión**: Eliminación de archivo
- **comando --help**: ayuda sobre el comando
- **git checkout**: traer cambios realizados
- **git rm --cached archivo.extensión**: se utiliza para devolver el archivo que se tiene en ram. Cuando escribimos git add, lo devuelve a estado natural mientras está en *staging*.
- **git config --list**: muestra la lista de configuración de git
- **git config --list --show-origin**: rutas de acceso a la configuración de git
- **git log archivo.extensión**: muestra la historia del archivo
- **git reset —hard:** con esto restauramos el arrchivo a la instantánea que queremos retornar según el código correspondiente (git reset --hard 29a1254)

Aporte creado por: Stefania Ortega
![Untitled 1](https://github.com/Gersa28/Git_GitHub_summary/assets/91088888/8e698b46-d1a2-47cd-a4c8-e00d226052f0)

![Untitled](Git%20y%20GitHub%20a7cd841d61cc4e0bb4d3c27f90bb55c5/Untitled%201.png)

Para salir del editor de texto: esc + shift + z +z

# 10_ ¿Qué es el staging?

Hay un concepto que a lo largo del curso esta mal. “El staging area esta en memoria”, y eso es absolutamente incorrecto. El staging area esta en el disco. Es persistente. Podes apagar o resetear la computadora, dejarla prendida 1000 años y no se va a borrar ya que esta en el disco, es persistente.[https://git-scm.com/book/en/v1/Getting-Started-Git-Basics](https://platzi.com/clases/1557-git-github/19935-flujo-de-trabajo-basico-con-un-repositorio-remoto/url)"**The staging area is a simple file**, generally contained in your Git directory, that stores information about what will go into your next commit. It’s sometimes referred to as the index, but it’s becoming standard to refer to it as the staging area."

**EPadronU23**

4

Es un grave error que se sigue repitiendo y magnificando. Ahora se afirma que está a la merced de un GC y se puede perder lo que se almacena en el *staging area*…

**Joaquin Antonio Juarez Barahona**

[Hace 2 años](https://platzi.com/comentario/753522/)

12

Totalmente de acuerdo es más, por experiencia lo digo, he dejado cosas en stage semanas y siguen ahí esperando a ser “commiteadas”.

El staging es el lugar donde se guardan temporalmente los cambios, para luego ser llevados definitivamente al repositorio. El repositorio es el lugar donde se guardan todos los registros de los cambios realizados a los archivos.

Para iniciar un repositorio, o sea, activar el sistema de control de versiones de Git en tu proyecto, solo debes ejecutar el comando git init.

## ¿Qué es el área de staging?

El área de staging se puede ver como un limbo donde nuestros archivos están por ser enviados al repositorio o ser regresados a la carpeta del proyecto.

## ¿Qué es git init?

git inites el comando que activa git en nuestro proyecto creando un espacio en memoria RAM llamado staging y una carpeta .git.

Este comando se encargará de dos cosas: primero, crear una carpeta .git, donde se guardará toda la base de datos con cambios atómicos de nuestro proyecto; segundo, crear un área que conocemos como **staging**, que guardará temporalmente nuestros archivos (cuando ejecutemos un comando especial para eso) y nos permitirá, más adelante, guardar estos cambios en el repositorio (también con un comando especial).

## Cómo funciona el staging y el repositorio: ciclo básico de trabajo en git:

El flujo de trabajo básico en git es algo así:

1. Modificas una serie de archivos en tu directorio de trabajo.
2. Preparas los archivos, añadiéndolos a tu área de preparación (staging).
3. Confirmas los cambios (commit), lo que toma los archivos tal y como están en el área de preparación y almacena esa copia instantánea de manera permanente en tu directorio de git.

Veamos a detalle las 3 secciones principales que tiene un proyecto en git.

### Working directory

El *working directory* es una copia de una versión del proyecto. Estos archivos se sacan de la base de datos comprimida en el directorio de git y se colocan en el disco para que los puedas usar o modificar.

### Staging area

Es un área que almacena información acerca de lo que va a ir en tu próxima confirmación. A veces se le denomina índice (*index*).

### .git directory (repository)

En el *repository* se almacenan los metadatos y la base de datos de los objetos para tu proyecto. Es la parte más importante de git (carpeta .git) y es lo que se copia cuando clonas un repositorio desde otra computadora.

## **Ciclo de vida o estados de los archivos en git**

Cuando trabajamos con git, nuestros archivos pueden vivir y moverse entre 4 diferentes estados (cuando trabajamos con repositorios remotos pueden ser más estados, pero lo estudiaremos más adelante):

### **Archivos tracked**

Son los archivos que viven dentro de git, no tienen cambios pendientes y sus últimas actualizaciones han sido guardadas en el repositorio gracias a los comandos git add y git commit.

### **Archivos staged**

Son archivos en staging. Viven dentro de git y hay registro de ellos porque han sido afectados por el comando git add, aunque no sus últimos cambios. Git ya sabe de la existencia de estos últimos cambios, pero todavía no han sido guardados definitivamente en el repositorio porque falta ejecutar el comando git commit.

### **Archivos unstaged**

Entiéndelos como archivos *“tracked* pero *unstaged”*. Son archivos que viven dentro de git pero no han sido afectados por el comando git add ni mucho menos por git commit. Git tiene un registro de estos archivos, pero está desactualizado, sus últimas versiones solo están guardadas en el disco duro.

### **Archivos untracked**

Son archivos que NO viven dentro de git, solo en el disco duro. Nunca han sido afectados por git add, así que git no tiene registros de su existencia.

Recuerda que hay un caso muy raro donde los archivos tienen dos estados al mismo tiempo: staged y untracked. Esto pasa cuando guardas los cambios de un archivo en el área de staging (con el comando git add), pero antes de hacer commit para guardar los cambios en el repositorio haces nuevos cambios que todavía no han sido guardados en el área de staging.

## **Comandos para mover archivos entre los estados de Git**

Estos son los comandos más importantes que debes conocer:

### Git status

**git status** nos permite ver el estado de todos nuestros archivos y carpetas.

### Git add

**git add** nos ayuda a mover archivos del untracked o unstaged al estado staged. Podemos usar git nombre-del-archivo-o-carpeta para añadir archivos y carpetas individuales o git add -A para mover todos los archivos de nuestro proyecto (tanto untrackeds como unstageds).

### G**it reset HEAD**

Nos ayuda a sacar archivos del estado staged para devolverlos a su estado anterior. Si los archivos venían de unstaged, vuelven allí. Y lo mismo se venían de untracked.

### G**it commit**

Nos ayuda a mover archivos de unstaged a tracked. Esta es una ocasión especial, los archivos han sido guardados o actualizados en el repositorio. Git nos pedirá que dejemos un mensaje para recordar los cambios que hicimos y podemos usar el argumento m para escribirlo (git commit -m "mensaje").

### G**it rm**

Este comando necesita alguno de los siguientes argumentos para poder ejecutarse correctamente:

- git rm --cached: mueve los archivos que le indiquemos al estado untracked.
- git rm --force: elimina los archivos de git y del disco duro. Git guarda el registro de la existencia de los archivos, por lo que podremos recuperarlos si es necesario (pero debemos usar comandos más avanzados).

**Contribución creada con los aportes de:** *Diego Camacho, Jesús Sarabia y Angelo Yenque.*

Analizar cambios en los archivos de tu proyecto con Git

El comando **git show** nos muestra los cambios que han existido sobre un archivo y es muy útil para detectar cuándo se produjeron ciertos cambios, qué se rompió y cómo lo podemos solucionar. Pero podemos ser más detallados.

Si queremos ver la diferencia entre una versión y otra, no necesariamente todos los cambios desde la creación del archivo, podemos usar el comando **git diff commitA commitB**.

Recuerda que puedes obtener el ID de tus commits con el comando **git log**.

## Comandos para analizar cambios en GIT

- **git init**: inicializar el repositorio
- **git add nombre_de_archivo.extensión**: agregar el archivo al repositorio
- **git commit -m “Mensaje”**: Agregamos los cambios para el repositorio
- **git add**: Agregar los cambios de la carpeta en la que nos encontramos agregar todo
- **git status**: visualizar cambios
- **git log nombre_de_archivos.extensión**: histórico de cambios con detalles
- **git log —oneline**: está muy bueno porque muestra todos los commits
- **git push**: envía a otro repositorio remoto lo que estamos haciendo
- **git pull**: traer repositorio remoto
- **ls**: listado de carpetas en donde me encuentro. Es decir, como emplear dir en windows.
- **pwd**: ubicación actual
- **mkdir**: make directory nueva carpeta
- **touch archivo.extensión**: crear archivo vacío
- **cat archivo.extensión**: muestra el contenido del archivo
- **history**: historial de comandos utilizados durante esa sesión
- **rm archivo.extensión**: Eliminación de archivo
- **comando --help**: ayuda sobre el comando
- **git checkout**: traer cambios realizados
- **git rm --cached archivo.extensión**: se utiliza para devolver el archivo que se tiene en ram. Cuando escribimos git add, lo devuelve a estado natural mientras está en *staging*.
- **git config --list**: muestra la lista de configuración de git
- **git config --list --show-origin**: rutas de acceso a la configuración de git
- **git log archivo.extensión**: muestra la historia del archivo
- **git commit —amend**: Cambiar mensaje de commit, con el editor VIM

10¿Qué es el staging y los repositorios? Ciclo básico de trabajo en Git

Para iniciar un repositorio, o sea, activar el sistema de control de versiones de Git en tu proyecto, solo debes ejecutar el comando git init.

Este comando se encargará de dos cosas: primero, crear una carpeta .git, donde se guardará toda la base de datos con cambios atómicos de nuestro proyecto; y segundo, crear un área que conocemos como Staging, que guardará temporalmente nuestros archivos (cuando ejecutemos un comando especial para eso) y nos permitirá, más adelante, guardar estos cambios en el repositorio (también con un comando especial).

**Ciclo de vida o estados de los archivos en Git**:

Cuando trabajamos con Git nuestros archivos pueden vivir y moverse entre 4 diferentes estados (cuando trabajamos con repositorios remotos pueden ser más estados, pero lo estudiaremos más adelante):

- **Archivos Tracked**: son los archivos que viven dentro de Git, no tienen cambios pendientes y sus últimas actualizaciones han sido guardadas en el repositorio gracias a los comandos git add y git commit.
- **Archivos Staged**: son archivos en Staging. Viven dentro de Git y hay registro de ellos porque han sido afectados por el comando git add, aunque no sus últimos cambios. Git ya sabe de la existencia de estos últimos cambios, pero todavía no han sido guardados definitivamente en el repositorio porque falta ejecutar el comando git commit.
- **Archivos Unstaged**: entiéndelos como archivos *“Tracked pero Unstaged”*. Son archivos que viven dentro de Git pero no han sido afectados por el comando git add ni mucho menos por git commit. Git tiene un registro de estos archivos, pero está desactualizado, sus últimas versiones solo están guardadas en el disco duro.
- **Archivos Untracked**: son archivos que NO viven dentro de Git, solo en el disco duro. Nunca han sido afectados por git add, así que Git no tiene registros de su existencia. Recuerda que hay un caso muy raro donde los archivos tienen dos estados al mismo tiempo: staged y untracked. Esto pasa cuando guardas los cambios de un archivo en el área de Staging (con el comando git add), pero antes de hacer commit para guardar los cambios en el repositorio haces nuevos cambios que todavía no han sido guardados en el área de Staging (en realidad, todo sigue funcionando igual pero es un poco divertido).

**Comandos para mover archivos entre los estados de Git**:

- **git status**: nos permite ver el estado de todos nuestros archivos y carpetas.
- **git add**: nos ayuda a mover archivos del Untracked o Unstaged al estado Staged. Podemos usar git nombre-del-archivo-o-carpeta para añadir archivos y carpetas individuales o git add -A para mover todos los archivos de nuestro proyecto (tanto Untrackeds como unstageds).
- **git reset HEAD**: nos ayuda a sacar archivos del estado Staged para devolverlos a su estado anterior. Si los archivos venían de Unstaged, vuelven allí. Y lo mismo se venían de Untracked.
- **git commit**: nos ayuda a mover archivos de Unstaged a Tracked. Esta es una ocasión especial, los archivos han sido guardados o actualizados en el repositorio. Git nos pedirá que dejemos un mensaje para recordar los cambios que hicimos y podemos usar el argumento -m para escribirlo (git commit -m "mensaje").
- **git rm**: este comando necesita alguno de los siguientes argumentos para poder ejecutarse correctamente: - git rm --cached: Mueve los archivos que le indiquemos al estado Untracked. - git rm --force: Elimina los archivos de Git y del disco duro. Git guarda el registro de la existencia de los archivos, por lo que podremos recuperarlos si es necesario (pero debemos usar comandos más avanzados).

Aporte creado por: Diego Camacho

Deshacer git de carpeta equivocada 1591

You can just delete .git. Typically:

rm -rf .git

# 11 Qué es un Branch (rama) y cómo funciona un Merge en Git?

Una **rama o branch** es una versión del código del proyecto sobre el que estás trabajando. Estas ramas ayudan a mantener el orden en el control de versiones y manipular el código de forma segura.

En otras palabras, un branch o rama en Git es una rama que proviene de otra. Imagina un árbol, que tiene una rama gruesa, y otra más fina, en la rama más gruesa tenemos los commits principales y en la rama fina tenemos otros commits que pueden ser de hotfix, devlopment entre otros.ㅤ

## Clases de branches o ramas en Git

Estas son las ramas base de un proyecto en Git:

### 1. Rama main (Master)

Por defecto, el proyecto se crea en una rama llamada Main (anteriormente conocida como Master). Cada vez que añades código y guardas los cambios, estás haciendo un commit, que es añadir el nuevo código a una rama. Esto genera nuevas versiones de esta rama o branch, hasta llegar a la versión actual de la rama Main.

### 2. Rama development

Cuando decides hacer experimentos, puedes generar ramas experimentales (usualmente llamadas development), que están basadas en alguna rama main, pero sobre las cuales puedes hacer cambios a tu gusto sin necesidad de afectar directamente al código principal.

### 3. Rama hotfix

En otros casos, si encuentras un bug o error de código en la rama Main (que afecta al proyecto en producción), tendrás que crear una nueva rama (que usualmente se llaman bug fixing o hot fix) para hacer los arreglos necesarios. Cuando los cambios estén listos, los tendrás que fusionar con la rama Main para que los cambios sean aplicados. Para esto, se usa un comando llamado *Merge*, que mezcla los cambios de la rama que originaste a la rama Main.

**Todos los commits se aplican sobre una rama**. Por defecto, siempre empezamos en la rama Main (pero puedes cambiarle el nombre si no te gusta) y generamos nuevas ramas, a partir de esta, para crear flujos de trabajo independientes.

## Cómo crear un branch o rama en Git

El comando git branch permite crear una rama nueva. Si quieres empezar a trabajar en una nueva función, puedes crear una rama nueva a partir de la rama master con git branch new_branch. Una vez creada, puedes usar git checkout new_branch para cambiar a esa rama.

Recuerda que todas tus versiones salen de la rama principal o Master y de allí puedes tomar una versión específica para crear otra rama de versiones.

## Cómo hacer merge

Producir una nueva rama se conoce como **Checkout**. Unir dos ramas lo conocemos como **Merge**.

Cuando haces merge de estas ramas con el código principal, su código se fusiona originando una nueva versión de la rama master (o main) que ya tiene todos los cambios que aplicaste en tus experimentos o arreglos de errores.

Podemos generar todas las ramas y commits que queramos. De hecho, podemos aprovechar el registro de cambios de Git para producir ramas, traer versiones viejas del código, arreglarlas y combinarlas de nuevo para mejorar el proyecto.

Solo ten en cuenta que combinar estas ramas ([hacer “merge”](https://platzi.com/clases/1557-git-github/19939-funcion-de-ramas-con-git-mer-7/)) puede generar conflictos. Algunos archivos pueden ser diferentes en ambas ramas. Git es muy inteligente y puede intentar unir estos cambios automáticamente, pero no siempre funciona. En algunos casos, somos nosotros los que debemos resolver estos conflictos *a mano*.

En GIT, una **rama o branch** es una versión del código del proyecto sobre el que estás trabajando. Estas ramas ayudan a mantener el orden en el control de versiones y manipular el código de forma segura. Por defecto, el proyecto se crea en una rama llamada Main (anteriormente conocida como Master). Cada vez que añades código y guardas los cambios, estás haciendo un commit, que es añadir el nuevo código a una rama. Esto genera nuevas versiones de esta rama o branch, hasta llegar a la versión actual de la rama Main.

Cuando decides hacer experimentos, puedes generar ramas experimentales (usualmente llamadas development), que están basadas en alguna rama main, pero sobre las cuales puedes hacer cambios a tu gusto sin necesidad de afectar directamente al código principal.

En otros casos, si encuentras un bug o error de código en la rama Main (que afecta al proyecto en producción), tendrás que crear una nueva rama (que usualmente se llaman bug fixing o hot fix) para hacer los arreglos necesarios. Cuando los cambios estén listos, los tendrás que fusionar con la rama Main para que los cambios sean aplicados. Para esto, se usa un comando llamado *Merge*, que mezcla los cambios de la rama que originaste a la rama Main.

**Todos los commits se aplican sobre una rama**. Por defecto, siempre empezamos en la rama Main (pero puedes cambiarle el nombre si no te gusta) y generamos nuevas ramas, a partir de esta, para crear flujos de trabajo independientes.

## Checkout y merge

Producir una nueva rama se conoce como **Checkout**. Unir dos ramas lo conocemos como **Merge**.

Cuando haces merge de estas ramas con el código principal, su código se fusiona, originando una nueva versión de la rama Master (o main) que ya tiene todos los cambios que aplicaste en tus experimentos o arreglos de errores.

Podemos generar todas las ramas y commits que queramos. De hecho, podemos aprovechar el registro de cambios de Git para producir ramas, traer versiones viejas del código, arreglarlas y combinarlas de nuevo para mejorar el proyecto.

Solo ten en cuenta que combinar estas ramas (hacer “merge”) puede generar conflictos. Algunos archivos pueden ser diferentes en ambas ramas. Git es muy inteligente y puede intentar unir estos cambios automáticamente, pero no siempre funciona. En algunos casos, somos nosotros los que debemos resolver estos conflictos *a mano*.

Aporte creado por: Diego García

Es muy importante tener un manejo ordenado de nuestro repositorio y para esto existe algo que se llama GitFlow.

GitFlow es una una guía que nos da cierto estándares para manejar la ramificación de nuestros proyectos, es decir, que ramas debemos tener, cuándo y de dónde debemos crear nuevas ramas, cómo debemos nombrar dichas ramas y muchos otros conceptos que nos ayudaran a manejar mucho mejor nuestro repositorio; siendo esto muy importante cuando trabajamos en conjunto con varios desarrolladores.

Algunos enlaces: [Gitflow Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)

[Git-Flow Cheatshee](https://danielkummer.github.io/git-flow-cheatsheet/)

Hola, han pasado ya 2 años desde el aporte original, pero al 2021 el empleo de git flow debe realizarse conociendo bien el proceso. El uso de flows o flujos aparece por necesidades especificas y define flujos de trabajo particulares

Existen otras opciones de flujos (4): git flow, github flow, gitlab flow y one flow que puede encontrase en [https://medium.com/@patrickporto/4-branching-workflows-for-git-30d0aaee7bf](https://medium.com/@patrickporto/4-branching-workflows-for-git-30d0aaee7bf)

Pueden encontrar pros y contrar de git flow en [https://www.toptal.com/software/trunk-based-development-git-flow](https://www.toptal.com/software/trunk-based-development-git-flow)

E incluso recomendaciones de no utilizar git flow en [https://about.gitlab.com/blog/2020/03/05/what-is-gitlab-flow/](https://about.gitlab.com/blog/2020/03/05/what-is-gitlab-flow/) y [https://georgestocker.com/2020/03/04/please-stop-recommending-git-flow/](https://georgestocker.com/2020/03/04/please-stop-recommending-git-flow/)

Y aqui una comparacion entre git flow y github flow [https://lucamezzalira.com/2014/03/10/git-flow-vs-github-flow/](https://lucamezzalira.com/2014/03/10/git-flow-vs-github-flow/)

Asi que podria recomendarse que es mejor utilizar los concpetos originales de banchs/ramas propios de git Saludos

El flujo de Gitflow es así:

En la rama **master** tendremos solo lo que se ha liberado.

1.- Se crea la rama **develop**, es la rama en la que estamos trabajando (lo que vamos a liberar).

2.- Liberar a producción con tu equipo de trabajo se crea una **release** desde develop.

No se pasa directo de develop a master, Git Flow crea la nueva rama de release.

3.- Por cada petición o tarea se genera una rama llamada **feature** a partir de develop.

4.- Por ejemplo una pantalla nueva, se crea y está completa el **feature** de pantalla se cierra y se afusiona con **develop**.

5.- Cuando tienes la rama release terminada, fusionas con develop y master.

6.- Si hay problema en master se crea **hotfix** que son los cambios sobre algo que está en producción.

7.- Se crea una nueva rama se trabaja y se reintegra. Una vez que hotfix se completa, se fusiona a ambos develop y master.

[Vídeo de consulta](https://www.youtube.com/watch?v=G_iTZtnlf_U)

Además de los enlaces de @hernan__giraldo

Volver en el tiempo en nuestro repositorio utilizando reset y checkout

Es muy importante tener un manejo ordenado de nuestro repositorio y para esto existe algo que se llama GitFlow.

GitFlow es una una guía que nos da cierto estándares para manejar la ramificación de nuestros proyectos, es decir, que ramas debemos tener, cuándo y de dónde debemos crear nuevas ramas, cómo debemos nombrar dichas ramas y muchos otros conceptos que nos ayudaran a manejar mucho mejor nuestro repositorio; siendo esto muy importante cuando trabajamos en conjunto con varios desarrolladores.

Algunos enlaces:[Gitflow Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)

[Git-Flow Cheatsheet](https://danielkummer.github.io/git-flow-cheatsheet/)

El flujo de Gitflow es así:

En la rama **master** tendremos solo lo que se ha liberado.

1.- Se crea la rama **develop**, es la rama en la que estamos trabajando (lo que vamos a liberar).

2.- Liberar a producción con tu equipo de trabajo se crea una **release** desde develop.

No se pasa directo de develop a master, Git Flow crea la nueva rama de release.

3.- Por cada petición o tarea se genera una rama llamada **feature** a partir de develop.

4.- Por ejemplo una pantalla nueva, se crea y está completa el **feature** de pantalla se cierra y se afusiona con **develop**.

5.- Cuando tienes la rama release terminada, fusionas con develop y master.

6.- Si hay problema en master se crea **hotfix** que son los cambios sobre algo que está en producción.

7.- Se crea una nueva rama se trabaja y se reintegra. Una vez que hotfix se completa, se fusiona a ambos develop y master.

[Vídeo de consulta](https://www.youtube.com/watch?v=G_iTZtnlf_U)

Además de los enlaces de @hernan__giraldo

Hola, han pasado ya 2 años desde el aporte original, pero al 2021 el empleo de git flow debe realizarse conociendo bien el proceso.El uso de flows o flujos aparece por necesidades especificas y define flujos de trabajo particulares

Existen otras opciones de flujos (4): git flow, github flow, gitlab flow y one flow que puede encontrase en [https://medium.com/@patrickporto/4-branching-workflows-for-git-30d0aaee7bf](https://medium.com/@patrickporto/4-branching-workflows-for-git-30d0aaee7bf)

Pueden encontrar pros y contrar de git flow en [https://www.toptal.com/software/trunk-based-development-git-flow](https://www.toptal.com/software/trunk-based-development-git-flow)

E incluso recomendaciones de no utilizar git flow en [https://about.gitlab.com/blog/2020/03/05/what-is-gitlab-flow/](https://about.gitlab.com/blog/2020/03/05/what-is-gitlab-flow/) y[https://georgestocker.com/2020/03/04/please-stop-recommending-git-flow/](https://georgestocker.com/2020/03/04/please-stop-recommending-git-flow/)

Y aqui una comparacion entre git flow y github flow[https://lucamezzalira.com/2014/03/10/git-flow-vs-github-flow/](https://lucamezzalira.com/2014/03/10/git-flow-vs-github-flow/)

Asi que podria recomendarse que es mejor utilizar los concpetos originales de banchs/ramas propios de gitSaludos

*Curso Profesional de Git y Github*

# 12_ Volver en el tiempo en nuestro repositorio utilizando reset y checkout

El comando **git checkout** + ID del commit nos permite viajar en el tiempo. Podemos volver a cualquier versión anterior de un archivo específico o incluso del proyecto entero. Esta también es la forma de crear ramas y movernos entre ellas.

También hay una forma de hacerlo un poco más “ruda”: usando el comando git reset. En este caso, no solo “volvemos en el tiempo”, sino que borramos los cambios que hicimos después de este commit.

Hay dos formas de usar git reset: con el argumento --hard, borrando toda la información que tengamos en el área de staging (y perdiendo todo para siempre). O, un poco más seguro, con el argumento --soft, que mantiene allí los archivos del área de staging para que podamos aplicar nuestros últimos cambios pero desde un commit anterior.

## Cómo usar Git Reset

Para volver a commits previos, borrando los cambios realizados desde ese commit, podemos utilizar:

- git reset --soft [SHA 1]: elimina los cambios hasta el staging area
- git reset --mixed [SHA 1]: elimina los cambios hasta el working area
- git reset --hard [SHA 1]: regresa hasta el commit del [SHA-1] Donde el SHA-1 es el identificador del commit

Salir de git log :

Volvemos al pasado de una manera agresiva, todo lo posterior se elimina.

![Untitled](Git%20y%20GitHub%20a7cd841d61cc4e0bb4d3c27f90bb55c5/Untitled%202.png)

![Untitled](Git%20y%20GitHub%20a7cd841d61cc4e0bb4d3c27f90bb55c5/Untitled%203.png)

![Untitled](Git%20y%20GitHub%20a7cd841d61cc4e0bb4d3c27f90bb55c5/Untitled%204.png)

# 13_ Git reset vs. Git rm

Git reset y git rm son comandos con utilidades muy diferentes, pero se pueden confundir muy fácilmente.

## git rm

Este comando nos ayuda a eliminar archivos de Git sin eliminar su historial del sistema de versiones. Esto quiere decir que si necesitamos recuperar el archivo solo debemos “viajar en el tiempo” y recuperar el último commit antes de borrar el archivo en cuestión.

Recuerda que git rm no puede usarse así nomás. Debemos usar uno de los flags para indicarle a Git cómo eliminar los archivos que ya no necesitamos en la última versión del proyecto:

- git rm --cached: Elimina los archivos de nuestro repositorio local y del área de staging, pero los mantiene en nuestro disco duro. Básicamente le dice a Git que deje de trackear el historial de cambios de estos archivos, por lo que pasaran a un estado untracked.
- git rm --force: Elimina los archivos de Git y del disco duro. Git siempre guarda todo, por lo que podemos acceder al registro de la existencia de los archivos, de modo que podremos recuperarlos si es necesario (pero debemos usar comandos más avanzados).

## git reset

Este comando nos ayuda a volver en el tiempo. Pero no como git checkout que nos deja ir, mirar, pasear y volver. Con git reset volvemos al pasado sin la posibilidad de volver al futuro. Borramos la historia y la debemos sobreescribir. No hay vuelta atrás.

Este comando es **muy peligroso** y debemos emplearlo solo en caso de emergencia. Recuerda que debemos usar alguna de estas dos opciones:

Hay dos formas de utilizar git reset: con el argumento --hard, borrando toda la información que tengamos en el área de staging (y perdiendo todo para siempre). O, un poco más seguro, con el argumento --soft, que mantiene allí los archivos del área de staging para que podamos aplicar nuestros últimos cambios pero desde un commit anterior.

- git reset --soft: Borramos todo el historial y los registros de Git pero guardamos los cambios que tengamos en Staging, así podemos aplicar las últimas actualizaciones a un nuevo commit.
- git reset --hard: Borra todo. Todo todito, absolutamente todo. Toda la información de los commits y del área de staging se borra del historial.

**¡Pero todavía falta algo!**

- git reset HEAD: Este es el comando para sacar archivos del área de staging. No para borrarlos ni nada de eso, solo para que los últimos cambios de estos archivos no se envíen al último commit, a menos que cambiemos de opinión y los incluyamos de nuevo en staging con git add, por supuesto.

## ¿Por qué esto es importante?

Imagina el siguiente caso:

Hacemos cambios en los archivos de un proyecto para una nueva actualización. Todos los archivos con cambios se mueven al área de staging con el comando git add. Pero te das cuenta de que uno de esos archivos no está listo todavía. Actualizaste el archivo, pero ese cambio no debe ir en el próximo commit por ahora.

¿Qué podemos hacer?

Bueno, todos los cambios están en el área de Staging, incluido el archivo con los cambios que no están listos. Esto significa que debemos sacar ese archivo de Staging para poder hacer commit de todos los demás.

¡Al usar git rm lo que haremos será eliminar este archivo completamente de git! Todavía tendremos el historial de cambios de este archivo, con la eliminación del archivo como su última actualización. Recuerda que en este caso no buscábamos eliminar un archivo, solo dejarlo como estaba y actualizarlo después, no en este commit.

En cambio, si usamos git reset HEAD, lo único que haremos será mover estos cambios de Staging a Unstaged. Seguiremos teniendo los últimos cambios del archivo, el repositorio mantendrá el archivo (no con sus últimos cambios, pero sí con los últimos en los que hicimos commit) y no habremos perdido nada.

**Conclusión**: Lo mejor que puedes hacer para salvar tu puesto y evitar un incendio en tu trabajo es conocer muy bien la diferencia y los riesgos de todos los comandos de Git.

# 14_ Flujo de trabajo básico con un repositorio remoto

Cuando empiezas a trabajar en un entorno local, el proyecto vive únicamente en tu computadora. Esto significa que no hay forma de que otros miembros del equipo trabajen en él.

Para solucionar esto, utilizamos los **servidores remotos**: un nuevo estado que deben seguir nuestros archivos para conectarse y trabajar con equipos de cualquier parte del mundo.

Estos servidores remotos pueden estar alojados en GitHub, GitLab, BitBucket, entre otros. Lo que van a hacer es guardar el mismo repositorio que tienes en tu computadora y darnos una URL con la que todos podremos acceder a los archivos del proyecto. Así, el equipo podrá descargarlos, hacer cambios y volverlos a enviar al servidor remoto para que otras personas vean los cambios, comparen sus versiones y creen nuevas propuestas para el proyecto.

Esto significa que debes aprender algunos nuevos comandos

## Comandos para trabajo remoto con GIT

- **git clone url_del_servidor_remoto**: Nos permite descargar los archivos de la última versión de la rama principal y todo el historial de cambios en la carpeta .git.
- **git push**: Luego de hacer git add y git commit debemos ejecutar este comando para mandar los cambios al servidor remoto.
- **git fetch**: Lo usamos para traer actualizaciones del servidor remoto y guardarlas en nuestro repositorio local (en caso de que hayan, por supuesto).
- **git merge**: También usamos el comando git merge con servidores remotos. Lo necesitamos para combinar los últimos cambios del servidor remoto y nuestro directorio de trabajo.
- **git pull**: Básicamente, git fetch y git merge al mismo tiempo.

Adicionalmente, tenemos otros comandos que nos sirven para trabajar en proyectos muy grandes:

- **git log --oneline**:Te muestra el id commit y el título del commit.
- **git log --decorate**: Te muestra donde se encuentra el head point en el log.
- **git log --stat**: Explica el número de líneas que se cambiaron brevemente.
- **git log -p**: Explica el número de líneas que se cambiaron y te muestra que se cambió en el contenido.
- **git shortlog**: Indica que commits ha realizado un usuario, mostrando el usuario y el título de sus commits.
- **git log --graph --oneline --decorate** y
- **git log --pretty=format:"%cn hizo un commit %h el dia %cd"**: Muestra mensajes personalizados de los commits.
- **git log -3**: Limitamos el número de commits.
- **git log --after=“2018-1-2”**
- **git log --after=“today”** y
- **git log --after=“2018-1-2” --before=“today”**: Commits para localizar por fechas.
- **git log --author=“Name Author”**: Commits hechos por autor que cumplan exactamente con el nombre.
- **git log --grep=“INVIE”**: Busca los commits que cumplan tal cual está escrito entre las comillas.
- **git log --grep=“INVIE” –i**: Busca los commits que cumplan sin importar mayúsculas o minúsculas.
- **git log – index.html**: Busca los commits en un archivo en específico.
- **git log -S “Por contenido”**: Buscar los commits con el contenido dentro del archivo.
- **git log > log.txt**: guardar los logs en un archivo txt

Algunos comandos que pueden ayudar cuando colaboren con proyectos muy grandes de github:

1. git log --oneline - Te muestra el id commit y el título del commit.
2. git log --decorate- Te muestra donde se encuentra el head point en el log.
3. git log --stat - Explica el número de líneas que se cambiaron brevemente.
4. git log -p- Explica el número de líneas que se cambiaron y te muestra que se cambió en el contenido.
5. git shortlog - Indica que commits ha realizado un usuario, mostrando el usuario y el titulo de sus commits.
6. git log --graph --oneline --decorate y
7. git log --pretty=format:"%cn hizo un commit %h el dia %cd" - Muestra mensajes personalizados de los commits.
8. git log -3 - Limitamos el número de commits.
9. git log --after=“2018-1-2” ,
10. git log --after=“today” y
11. git log --after=“2018-1-2” --before=“today” - Commits para localizar por fechas.
12. git log --author=“Name Author” - Commits realizados por autor que cumplan exactamente con el nombre.
13. git log --grep=“INVIE” - Busca los commits que cumplan tal cual está escrito entre las comillas.
14. git log --grep=“INVIE” –i- Busca los commits que cumplan sin importar mayúsculas o minúsculas.
15. git log – index.html- Busca los commits en un archivo en específico.
16. git log -S “Por contenido”- Buscar los commits con el contenido dentro del archivo.
17. git log > log.txt - guardar los logs en un archivo txt

VER PDF EN CARPETA DE CURSO CLASE 14.

![Untitled](Git%20y%20GitHub%20a7cd841d61cc4e0bb4d3c27f90bb55c5/Untitled%205.png)

![Untitled](Git%20y%20GitHub%20a7cd841d61cc4e0bb4d3c27f90bb55c5/Untitled%206.png)

![Untitled](Git%20y%20GitHub%20a7cd841d61cc4e0bb4d3c27f90bb55c5/Untitled%207.png)

![Untitled](Git%20y%20GitHub%20a7cd841d61cc4e0bb4d3c27f90bb55c5/Untitled%208.png)

![Untitled](Git%20y%20GitHub%20a7cd841d61cc4e0bb4d3c27f90bb55c5/Untitled%209.png)

![Untitled](Git%20y%20GitHub%20a7cd841d61cc4e0bb4d3c27f90bb55c5/Untitled%2010.png)

![Untitled](Git%20y%20GitHub%20a7cd841d61cc4e0bb4d3c27f90bb55c5/Untitled%2011.png)

# 15_ Introducción a las ramas o branches de Git

Las ramas [(branches)](https://platzi.com/clases/1557-git-github/19947-que-es-un-branch-rama-y-como-funciona-un-merge-en-/) son la forma de hacer cambios en nuestro proyecto sin afectar el flujo de trabajo de la rama principal. Esto porque queremos trabajar una parte muy específica de la aplicación o simplemente experimentar.

La cabecera o HEAD representan la rama y el commit de esa rama donde estamos trabajando. Por defecto, esta cabecera aparecerá en el último commit de nuestra rama principal.

Pero podemos cambiarlo al crear una rama (git branch rama, git checkout -b rama) o movernos en el tiempo a cualquier otro commit de cualquier otra rama con los comandos (git reset id-commit, git checkout rama-o-id-commit).

## Cómo funcionan las ramas en GIT

Las ramas son la manera de hacer cambios en nuestro proyecto sin afectar el flujo de trabajo de la rama principal. Esto porque queremos trabajar una parte muy específica de la aplicación o simplemente experimentar.

- **git branch -nombre de la rama-**: Con este comando se genera una nueva rama.
- **git checkout -nombre de la rama-**: Con este comando puedes saltar de una rama a otra.
- **git checkout -b rama**: Genera una rama y nos mueve a ella automáticamente, Es decir, es la combinación de git brach y git checkout al mismo tiempo.
- **git reset id-commit**: Nos lleva a cualquier commit no importa la rama, ya que identificamos el id del tag., eliminando el historial de los commit posteriores al tag seleccionado.
- **git checkout rama-o-id-commit**: Nos lleva a cualquier commit sin borrar los commit posteriores al tag seleccionado.

# 16_ Fusión de ramas con Git merge

El comando git merge nos permite crear un nuevo *commit* con la combinación de dos ramas o [branches](https://platzi.com/clases/1557-git-github/19947-que-es-un-branch-rama-y-como-funciona-un-merge-en-/) (la rama donde nos encontramos cuando ejecutamos el comando y la rama que indiquemos después del comando).

## Cómo usar Git merge

En este ejemplo, vamos a crear un nuevo *commit* en la rama *master* combinando los cambios de una rama llamada *cabecera*:

git checkout

**master**

**git**

merge cabecera

Otra opción es crear un nuevo *commit* en la rama *cabecera* combinando los cambios de cualquier otra rama:

git checkout cabeceragit

**merge**

cualquier-otra-rama

Asombroso, ¿verdad? Es como si Git tuviera superpoderes para saber qué cambios queremos conservar de una rama y qué otros de la otra. El problema es que no siempre puede adivinar, sobre todo en algunos casos donde dos ramas tienen actualizaciones diferentes en ciertas líneas en los archivos. Esto lo conocemos como un **conflicto**.

Recuerda que al ejecutar el comando git checkout para cambiar de rama o *commit* puedes perder el trabajo que no hayas guardado. **Guarda siempre tus cambios antes de hacer git checkout**.

## Comandos básicos de GitHub

- git init: crear un repositorio.
- git add: agregar un archivo a staging.
- git commit -m “mensaje”: guardar el archivo en git con un mensaje.
- git branch: crear una nueva rama.
- git checkout: moverse entre ramas.
- git push: mandar cambios a un servidor remoto.
- git fetch: traer actualizaciones del servidor remoto y guardarlas en nuestro repositorio local.
- git merge: tiene dos usos. Uno es la fusión de ramas, funcionando como un *commit* en la rama actual, trayendo la rama indicada. Su otro uso es guardar los cambios de un servidor remoto en nuestro directorio.
- git pull: fetch y merge al mismo tiempo.

## Comandos para corrección en GitHub

- git checkout “codigo de version” “nombre del archivo”: volver a la última versión de la que se ha hecho *commit*.
- git reset: vuelve al pasado sin posibilidad de volver al futuro, se debe usar con especificaciones.
- git reset --soft: vuelve a la versión en el repositorio, pero guarda los cambios en staging. Así, podemos aplicar actualizaciones a un nuevo *commit*.
- git reset --hard: todo vuelve a su versión anterior
- git reset HEAD: saca los cambios de staging, pero no los borra. Es lo opuesto a git add.
- git rm: elimina los archivos, pero no su historial. Si queremos recuperar algo, solo hay que regresar. se utiliza así: git rm --cached elimina los archivos en staging pero los mantiene en el disco duro. git rm --force elimina los archivos de git y del disco duro.

## Comandos para revisión y comparación en GitHub

- git status: estado de archivos en el repositorio.
- git log: historia entera del archivo.
- git log --stat: cambios específicos en el archivo a partir de un commit.
- git show: cambios históricos y específicos hechos en un archivo.
- git diff “codigo de version 1” “codigo de version 2”: comparar cambios entre versiones.
- git diff: comparar directorio con *staging*.

Comparo mis apuntes hasta el momento

Utilizo una tablet, ya llevo unos años con ella (Unos 3 o 4 años). Es la Samsung Galaxy Tab A 8.0, para hacer los apuntes.

Responder

# 17_ Resolución de conflictos al hacer un merge

**Git nunca borra nada**, a menos que nosotros se lo indiquemos. Cuando usamos los comandos git merge o git checkout estamos cambiando de rama o creando un nuevo *commit*, no borrando ramas ni *commits* (recuerda que puedes borrar commits con git reset y ramas con git branch -d).

Git es muy inteligente y puede resolver algunos conflictos automáticamente: cambios, nuevas líneas, entre otros. Pero algunas veces no sabe cómo resolver estas diferencias, por ejemplo, cuando dos ramas diferentes hacen cambios distintos a una misma línea.

Esto lo conocemos como **conflicto** y lo podemos resolver manualmente. Solo debemos hacer el *merge*, ir a nuestro editor de código y elegir si queremos quedarnos con alguna de estas dos versiones o algo diferente. Algunos editores de código como Visual Studio Code nos ayudan a resolver estos conflictos sin necesidad de borrar o escribir líneas de texto, basta con hacer clic en un botón y guardar el archivo.

Recuerda que siempre debemos crear un nuevo commit para aplicar los cambios del merge. Si Git puede resolver el conflicto, hará commit automáticamente. Pero, en caso de que no pueda resolverlo, debemos solucionarlo y hacer el commit.

Los archivos con conflictos por el comando git merge entran en un nuevo estado que conocemos como *Unmerged*. Funcionan muy parecido a los archivos en estado *Unstaged*, algo así como un estado intermedio entre Untracked y Unstaged. Solo debemos ejecutar git add para pasarlos al área de staging y git commit para aplicar los cambios en el repositorio.

## Cómo revertir un merge

Si nos hemos equivocado y queremos cancelar el merge, debemos usar el siguiente comando:

git merge –abort

## Conflictos en repositorios remotos

Al trabajar con otras personas, es necesario utilizar un repositorio remoto. ­ -Para copiar el repositorio remoto al directorio de trabajo local, se utiliza el comando git clone `<url>`, y para enviar cambios al repositorio remoto se utiliza git push. -Para actualizar el repositorio local se hace uso del comando git fetch, luego se debe fusionar los datos traídos con los locales usando git merge.

- Para traer los datos y fusionarlos a la vez, en un solo comando, se usa git pull. ­- Para crear commits rápidamente, fusionando git add y git commit -m "", usamos git commit -am "". ­- Para generar nuevas ramas, hay que posicionarse sobre la rama que se desea copiar y utilizar el comando git branch `<nombre>`.
- Para saltar entre ramas, se usa el comando git checkout `<branch>` ­- Una vez realizado los cambios en la rama, estas deben fusionarse con git merge.
- El merge ocurre en la rama en la que se está posicionado. Por lo tanto, la rama a fusionar se transforma en la principal.
- Los merges también son commits.
- Los merges pueden generar conflictos, esto aborta la acción y pide que soluciones el problema manualmente, aceptando o rechazando los cambios que vienen.

Aporte creado por: José Tuzinkievicz, Lottie

Los merge funcionan en uno u otra dirección, vamos a simular un conflicto:

# 18_ Cambios en GitHub: de master a main

Desde el 1 de octubre de 2020 GitHub cambió el nombre de la rama principal: ya no es “master” -como aprenderás en el curso- sino main.

Es más fácil cambiarle el nombre en git de Master a main con el comando

Renombrar la rama master a Main:

git Branch -m master main

y listo.

# 19_ Uso de GitHub

Es más fácil cambiarle el nombre en git de Master a main con el comando

Renombrar la rama master a Main:

git branch -m master main

y listo.

(Excelente GER)

Para comprobar:

git branch

**GitHub** es una plataforma que nos permite guardar repositorios de Git que podemos usar como servidores remotos y ejecutar algunos comandos de forma visual e interactiva (sin necesidad de la consola de comandos).

Luego de crear nuestra cuenta, podemos crear o importar repositorios, crear organizaciones y proyectos de trabajo, descubrir repositorios de otras personas, contribuir a esos proyectos, dar estrellas y muchas otras cosas.

El README.md es el archivo que veremos por defecto al entrar a un repositorio. Es una muy buena práctica configurarlo para describir el proyecto, los requerimientos y las instrucciones que debemos seguir para contribuir correctamente.

Para clonar un repositorio desde GitHub (o cualquier otro servidor remoto) debemos copiar la URL (por ahora, usando HTTPS) y ejecutar el comando git clone + la URL que acabamos de copiar. Esto descargará la versión de nuestro proyecto que se encuentra en GitHub.

Sin embargo, esto solo funciona para las personas que quieren empezar a contribuir en el proyecto.

## Cómo conectar un repositorio de GitHub a nuestro documento local

Si queremos conectar el repositorio de GitHub con nuestro repositorio local, que creamos usando el comando git init, debemos ejecutar las siguientes instrucciones:

- 1. Guardar la URL del repositorio de GitHub con el nombre de origin

git remote add origin URL

- 1. Verificar que la URL se haya guardado correctamente:

git remotegit remote -v

- 1. Traer la versión del repositorio remoto y hacer *merge* para crear un *commit* con los archivos de ambas partes. Podemos usar git fetch y git merge o solo git pull con el *flag* --allow-unrelated-histories:

git pull origin

**master**

- -allow-unrelated-histories
- 1. Por último, ahora sí podemos hacer git push para guardar los cambios de nuestro repositorio local en GitHub:

git push origin

**master**

```bash
git config --global init.default Branch main

```

Encontré ese comando para que todos los nuevos repositorios sean por default main y no estar haciendo

```bash
git branch -m master main
```

## Cómo autenticarte en GitHub 2022

Antes de empezar debemos renombrar la rama ‘máster’ a ‘main’, este es el nuevo estándar en GitHub, para esto:

1. Primero nos posicionamos en la rama a la que queremos cambiarle el nombre.
2. Ejecutamos el siguiente comando: git branch -M main

**Pasos para crear un token de acceso personal.**

**Desde el 2022 GitHub** ya no deja hacer el push con la contraseña del propio GitHub, para esto tenemos que crear un token, y este token es la contraseña que vamos a colocar cuando nos pida clave

Seguir la secuencia: Ingresamos a nuestra cuenta de GitHub.

1. Buscamos Settings
2. Click en Developer settings
3. Click en Personal access tokens
4. Click en Generate new token aquí se puede colocar un nombre, la fecha de expiración.
5. Tildar en repo y luego click en el botón verde Generate token

Si a ustedes no les sale el mensaje de que se tiene que traer los cambios y al intentar hacer el pull les dice que todo está actualizado es porque GitHub cambió su rama por defecto a “main” y nosotros estamos trabajando con la rama master, por tanto GitHub lo está tomando como un pull request (Porque son iferentes ramas)

Para seguir esta clase deben borrar el repositorio en GitHub (Si ya lo tenían creado) y configurar su rama por defecto como master en:

[https://github.com/settings/repositories](https://github.com/settings/repositories)

En el apartado “Repository default branch” borran main y escriben “master” y le dan al botón de actualizar, después vuelven a crear su repositorio “hyperblog” en GitHub y continuan la clase normal

Muchachos, a tener en cuenta: GitHub en Octubre 2020 decide llamar la rama ‘master’ a rama ‘main’, lo que significa que en cuanto a la clase han ocurrido algunos cambios.

Al ejecutar el comando:

git push origin **master**

Estamos diciéndole a git que envíe a origin (remoto) la rama ‘master’ de nuestro repositorio local. Por lo tanto, en GitHub se interpreta como adicionar una rama independiente llamada ‘master’ con su contenido a bordo, pero no se carga en la rama default de GitHub, debido a que su rama default ahora se llama ‘main’. Para alinear el contenido de Freedy y la actualización de GitHub, en la practica el comando para realizar el push según el nuevo estándar seria:

git push origin master:main

En donde le estamos diciéndole a git que envíe a origin (remoto) la rama ‘master’ de nuestro repositorio local hasta la rama ‘main’ del servidor remoto. De igual manera, dentro de esta nueva lógica:

git pull origin main --allow-unrelated-histories

En donde estamos trayendo desde el servidor remoto la rama ‘main’ fusionando las historias. De tal manera que ya podemos continuar con el contenido de Freddy sin llegar a confundirnos.

Desde el 1 de octubre de 2020 GitHub cambió el nombre de la rama principal: ya no es “master” -como aprenderás en el curso- sino main.

Si continuas con la rama master y tienes cambios puedes utilizar el siguiente comando:

git **branch** -M main

- M = mueve todos los cambios existentes en tu rama master a la nueva rama main

# 20_ Cómo funcionan las llaves públicas y privadas

Las **llaves públicas y privadas**, conocidas también como cifrado asimétrico de un solo camino, sirven para mandar mensajes privados entre varios nodos con la lógica de que firmas tu mensaje con una llave pública vinculada con una llave privada que puede leer el mensaje.

Las llaves públicas y privadas nos ayudan a cifrar y descifrar nuestros archivos de forma que los podamos compartir sin correr el riesgo de que sean interceptados por personas con malas intenciones.

## Cómo funciona un mensaje cifrado con llaves públicas y privadas

1. Ambas personas deben crear su llave pública y privada.

1. Ambas personas pueden compartir su llave pública a las otras partes (recuerda que esta llave es pública, no hay problema si la “interceptan”).

1. La persona que quiere compartir un mensaje puede usar la llave pública de la otra persona para cifrar los archivos y asegurarse que solo puedan ser descifrados con la llave privada de la persona con la que queremos compartir el mensaje.

1. El mensaje está cifrado y puede ser enviado a la otra persona sin problemas en caso de que los archivos sean interceptados.

1. La persona a la que enviamos el mensaje cifrado puede emplear su llave privada para descifrar el mensaje y ver los archivos.

Nota: puedes compartir tu llave pública, pero nunca tu llave privada.

Aporte creado por: David Behar

### **Archivos de la clase**

[llavespubpriv.png](https://static.platzi.com/media/public/uploads/llavespubpriv_9010b33d-d065-4610-8305-156c13a368b3.PNG)

![Untitled](Git%20y%20GitHub%20a7cd841d61cc4e0bb4d3c27f90bb55c5/Untitled%2012.png)

![Untitled](Git%20y%20GitHub%20a7cd841d61cc4e0bb4d3c27f90bb55c5/Untitled%2013.png)

# 21_ Configura tus llaves SSH en local

En este ejemplo, aprenderemos **cómo configurar nuestras llaves SSH en local**.

## Cómo generar tus llaves SSH

### 1. Generar tus llaves SSH**

Recuerda que es muy buena idea proteger tu llave privada con una contraseña.

ssh-keygen -t rsa -**b** 4096 -C [tu@email.com](mailto:tu@email.com)

### 2. Terminar de configurar nuestro sistema.

**En Windows y Linux**:

- Encender el “servidor” de llaves SSH de tu computadora:

**eval $(ssh-agent -s)** # Esto significa que el servidor SSH está encendido, o se encenderá

- Añadir tu llave SSH a este “servidor”:

ssh-**add** ruta-donde-guardaste-tu-**llave-privada**

**En Mac**:

- Encender el “servidor” de llaves SSH de tu computadora:

eval "$(ssh-agent -s)"

Si usas una versión de OSX superior a Mac Sierra (v10.12), debes crear o modificar un archivo “config” en la carpeta de tu usuario con el siguiente contenido (ten cuidado con las mayúsculas): Host *

AddKeysToAgent

**yes**

UseKeychain

**yes**

IdentityFile ruta-donde-guardaste-tu-llave-privada

- Añadir tu llave SSH al “servidor” de llaves SSH de tu computadora (en caso de error puedes ejecutar este mismo comando pero sin el argumento -K):

ssh-

**add**

- K ruta-donde-guardaste-tu-

**llave-privada**

Aporte creado por: Juan Luis Rojas

### **Archivos de la clase**

[git-github-29-36.pdf](https://static.platzi.com/media/public/uploads/git-github-29-36_15689cef-fbdf-4caf-a980-128fae551474.pdf)

[config.txt](https://static.platzi.com/media/public/uploads/config_7ca3323c-f646-4231-a0a1-b5cd4d3fb843.txt)

**Generar una nueva llave SSH: (Cualquier sistema operativo)**

ssh-keygen -t rsa -b 4096 -C "youremail@example.com"

**Comprobar proceso y agregarlo (Windows)**

- eval $(ssh-agent - s) #iniciamos servidor SSH
- ssh-add ~/.ssh/id_rsa #ruta de llave privada, aca agregamos la llave
- ***(/c/Users/INGENIERO SALINA/.ssh/id_rsa) (usamos el signo cd~ y listo, nos lleva al directorio automáticamente)***

![Untitled](Git%20y%20GitHub%20a7cd841d61cc4e0bb4d3c27f90bb55c5/Untitled%2014.png)

![Untitled](Git%20y%20GitHub%20a7cd841d61cc4e0bb4d3c27f90bb55c5/Untitled%2015.png)

![Untitled](Git%20y%20GitHub%20a7cd841d61cc4e0bb4d3c27f90bb55c5/Untitled%2016.png)

**Comprobar proceso y agregarlo (Mac)**

- eval "$(ssh-agent -s)"

*¿Usas macOS Sierra 10.12.2 o superior?* *Haz lo siguiente:*

- cd ~/.ssh
- Crea un archivo config…
- Con Vim vim config
- Con VSCode code config
- Pega la siguiente configuración en el archivo…

Host *

AddKeysToAgent **yes**

UseKeychain **yes**

IdentityFile ~/.ssh/id_rsa

Agrega tu llave

ssh-add -K ~/.ssh/id_rsa

**Generar una nueva llave SSH: (Cualquier sistema operativo)**

`ssh-keygen -t rsa -b 4096 -C "youremail@example.com"`

**Comprobar proceso y agregarlo (Windows)**

- `eval $(ssh-agent - s)`
- `ssh-add ~/.ssh/id_rsa`

**Comprobar proceso y agregarlo (Mac)**

- `eval "$(ssh-agent -s)"`

*¿Usas macOS Sierra 10.12.2 o superior?Haz lo siguiente:*

- `cd ~/.ssh`
- Crea un archivo config…
- Con Vim `vim config`
- Con VSCode `code config`
- Pega la siguiente configuración en el archivo…

```
Host *
  AddKeysToAgentyes
  UseKeychainyes
  IdentityFile ~/.ssh/id_rsa

```

Agrega tu llave

`ssh-add -K ~/.ssh/id_rsa`🥳

![Untitled](Git%20y%20GitHub%20a7cd841d61cc4e0bb4d3c27f90bb55c5/Untitled%2017.png)

# 22 Conexión a GitHub con SSH

La creación de las SSH es necesario solo una vez por cada computadora (TRES COMPUS TRES LLAVES). Aquí conocerás **cómo conectar a GitHub usando SSH**.

Luego de crear nuestras llaves SSH podemos entregarle la llave pública a GitHub para comunicarnos de forma segura y sin necesidad de escribir nuestro usuario y contraseña todo el tiempo.

Para esto debes entrar a la [Configuración de Llaves SSH en GitHub](https://github.com/settings/keys), crear una nueva llave con el nombre que le quieras dar y el contenido de la llave pública de tu computadora.

Ahora podemos actualizar la URL que guardamos en nuestro repositorio remoto, solo que, en vez de guardar la URL con HTTPS, vamos a usar la URL con SSH:

```bash
ssh
git remoteset-url originurl-ssh-del-repositorio-en-github

```

## Comandos para copiar la llave SSH:

- **Mac**:

```bash
pbcopy < ~/.ssh/id_rsa.pub

```

- **Windows (Git Bash)**:

```bash
clip < ~/.ssh/id_rsa.pub

```

- **Linux (Ubuntu)**:

```bash
cat ~/.ssh/id_rsa.pub

```

![Untitled](Git%20y%20GitHub%20a7cd841d61cc4e0bb4d3c27f90bb55c5/Untitled%2018.png)

![Untitled](Git%20y%20GitHub%20a7cd841d61cc4e0bb4d3c27f90bb55c5/Untitled%2019.png)

# 23 Tags y versiones GIT y GITHUB

Los tags o etiquetas nos permiten asignar versiones a los commits con cambios más importantes o significativos de nuestro proyecto.

## Comandos para trabajar con etiquetas:

- Crear un nuevo tag y asignarlo a un commit: **`git tag -a nombre-del-tag id-del-commit`**.
- Borrar un tag en el repositorio local: **`git tag -d nombre-del-tag`**.
- Listar los tags de nuestro repositorio local: **`git tag`** o **`git show-ref --tags`**.
- Publicar un tag en el repositorio remoto: **`git push origin --tags`**.
- Borrar un tag del repositorio remoto: `git tag -d nombre-del-tag` y **`git push origin :refs/tags/nombre-del-tag`**.

Para generar un comando complejo con varios comandos de una forma optimizada, utilizamos conjuntos de sentencias conocidas como *alias*.

## Cómo aregar un alias solo para git

- Para un proyecto:

```
git config alias.arbolito "log --all --graph --decorate --oneline"

```

- Global:

```
git config --global alias.arbolito "log --all --graph --decorate --oneline"

```

- Para correrlo:

```
git arbolito

```

Aporte creado por: Jorge Sarabia

Ejecutan este comando en la terminal y queda guardado en los alias pero de git. con esto se puede ejecutar cada que se escribe git superlog

```
git config --global alias.superlog "log --graph --abbrev-commit --decorate --date=relative --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --all"

```

![Untitled](Git%20y%20GitHub%20a7cd841d61cc4e0bb4d3c27f90bb55c5/Untitled%2020.png)

A mi me gusta usar GitKraken como interfaz gráfica. Es fácil de usar y muy interactiva. Pero a la hora del manejo de mis ramas y trabajo con repositorios remotos sigo usando la consola. Me parece mas rápido el uso de la consola y me siento más cómodo con ella, GitKraken lo uso para hacer mis commits y para revisar las diferencias de mi código de forma más amigable. Pero no deja de ser una herramienta muy poderosa para facilitar el trabajo a los desarrolladores. Deberían probarla.

![https://static.platzi.com/media/user_upload/gitkraken-69826fb6-7a04-4623-86ea-bf13e9258d17.jpg](https://static.platzi.com/media/user_upload/gitkraken-69826fb6-7a04-4623-86ea-bf13e9258d17.jpg)

También tiene otras herramientas. No sustituye el uso de la consola pero deberían darle una oportunidad.[https://www.gitkraken.com/](https://www.gitkraken.com/)

# 24 RAMAS EN GITHUB

Si no te funciona el comando gitk es posible no lo tengas instalado por defecto.Para instalar gitk debemos ejecutar los siguientes comandos:`sudo apt-get updatesudo apt-get install gitk`

Las ramas nos permiten hacer cambios a nuestros archivos sin modificar la versión principal (master). Puedes trabajar con ramas que nunca envías a GitHub, así como pueden haber ramas importantes en GitHub que nunca usas en el repositorio local. Lo crucial es que aprendas a manejarlas para trabajar profesionalmente.

Si, estando en otra rama, modificamos los archivos y hacemos *commit*, tanto el historial(`git log`) como los archivos serán afectados. La ventaja que tiene usar ramas es que las modificaciones solo afectarán a esa rama en particular. Si luego de “guardar” los archivos(usando `commit`) nos movemos a otra rama (`git checkout otraRama`) veremos como las modificaciones de la rama pasada **no aparecen** en la `otraRama`.

## Comandos para manejo de ramas en GitHub

- Crear una rama:`git branch branchName`
- Movernos a otra rama:`git checkout branchName`
- Crear una rama en el repositorio local:`git branch nombre-de-la-rama` o `git checkout -b nombre-de-la-rama`.
- Publicar una rama local al repositorio remoto:`git push origin nombre-de-la-rama`.

Recuerda que podemos ver gráficamente nuestro entorno y flujo de trabajo local con Git utilizando el comando `gitk`. Gitk fue el primer visor gráfico que se desarrolló para ver de manera gráfica el historial de un repositorio de Git.

> Repasa: Qué es branch.

![Untitled](Git%20y%20GitHub%20a7cd841d61cc4e0bb4d3c27f90bb55c5/Untitled%2021.png)

![Untitled](Git%20y%20GitHub%20a7cd841d61cc4e0bb4d3c27f90bb55c5/Untitled%2022.png)

Otro comando para crear una rama y moverse automaticamente a ella es con

```
git checkout-b <nombre de la rama>
```

Les comparto mi resumen “resumido”: Si tienen alguna duda con los comandos en la parte superior de la foto te dice a donde debes dirigirte. Let’s go !

![Untitled](Git%20y%20GitHub%20a7cd841d61cc4e0bb4d3c27f90bb55c5/Untitled%2023.png)

## Muchas veces nos confundimos sobre los branchs que se encuentran en *local* y en *remoto*.

Si yo ejecuto el comando

```
gitbranch

```

Nos mostrará las ramas que se encuentran en nuestro repositorio local. El * nos indica en que rama nos encontramos actualmente.

```
$ git branch
  cabecera
  footer
  header
master* stylesux
```

Para poder visualizar las ramas que se encuentran en el repositorio remoto, podemos utilizar el siguiente comando.

```
gitbranch-r

```

Esto nos mostrará las ramas que se encuentran en el repositorio remoto y podemos identificar si es que nos hace falta hacer push de alguna otra rama o simplemente dejar asi como se encuentra.

```
$ gitbranch-r
origin/cabecera
origin/footer
origin/header
origin/master
```

Si ejecutaste

*git pull origin master*

en la rama **cabecera** antes de enviarla a Github igual que yo, no te aflijas, te propongo la solución gracias a lo aprendido en el curso hasta ahora:

- Ejecuta

*git log*

para ver el historial, y regresa hasta el último commit que realizaste en la branch cabecera.

- Ve a la rama cabecera con

*git checkout cabecera*

- Haz un reset para regresar a esa rama

*git reset **uidcommit** --soft*

- Bien, ahora solo falta hacer el

*git push origin cabecera*

y podrás seguir con el curso bien 😉

## Borrar RAMA

![Untitled](Git%20y%20GitHub%20a7cd841d61cc4e0bb4d3c27f90bb55c5/Untitled%2024.png)

# 25 Configurar múltiples colaboradores en un repositorio GitHUB

Por defecto, cualquier persona puede clonar o descargar tu proyecto desde GitHub, pero no pueden crear commits, ni ramas. Esto quiere decir que pueden copiar tu proyecto pero no colaborar con él. Existen varias formas de solucionar esto para poder aceptar contribuciones. Una de ellas es añadir a cada persona de nuestro equipo como colaborador de nuestro repositorio.

## Cómo agregar colaboradores en Github

- Solo debemos entrar a la configuración de colaboradores de nuestro proyecto. Se encuentra en:`Repositorio > Settings > Collaborators`

Ahí, debemos añadir el email o username de los nuevos colaboradores.

![https://static.platzi.com/media/user_upload/collaborator-ccc98946-723f-4866-bd45-babd1163d987.jpg](https://static.platzi.com/media/user_upload/collaborator-ccc98946-723f-4866-bd45-babd1163d987.jpg)

Si, como colaborador, agregaste erróneamente el mensaje del *commit*, lo puedes cambiar de la siguiente manera:

- Hacer un *commit* con el nuevo mensaje que queremos, esto nos abre el editor de texto de la terminal:`git commit —amend`
- Corregimos el mensaje
- Traer el repositorio remoto `git pull origin master`
- Ejecutar el cambio `git push --set-upstream origin master`

Aporte creado por: Andrés Zambrano

![Untitled](Git%20y%20GitHub%20a7cd841d61cc4e0bb4d3c27f90bb55c5/Untitled%2025.png)

![Untitled](Git%20y%20GitHub%20a7cd841d61cc4e0bb4d3c27f90bb55c5/Untitled%2026.png)

Pobre anita ! Pero para que no te pase como anita, y te regañe freddy les comparto los comandos utilizados en el curso

[https://github.com/guajardo/Comandos-git](https://github.com/guajardo/Comandos-git)

![Untitled](Git%20y%20GitHub%20a7cd841d61cc4e0bb4d3c27f90bb55c5/Untitled%2027.png)

# 28 **Utilizando Pull Requests en GitHub**

**Pull request** es una funcionalidad de Github (en Gitlab llamada *merge request* y en Bitbucket *push request*), en la que un colaborador pide que revisen sus cambios antes de hacer *merge* a una rama, normalmente *master* (ahora conocida como *main*).

Al hacer un pull request, se genera una conversación que pueden seguir los demás usuarios del repositorio, así como autorizar y rechazar los cambios.

## Cómo se realiza un pull request

- Se trabaja en una rama paralela los cambios que se desean `git checkout -b <rama>`.
- Se hace un commit a la rama `git commit -am '<Comentario>'`.
- Se suben al remoto los cambios `git push origin <rama>`.
- En GitHub se hace el pull request comparando la rama master con la rama del fix.
- Uno, o varios colaboradores revisan que el código sea correcto y dan feedback (en el chat del pull request).
- El colaborador hace los cambios que desea en la rama y lo vuelve a subir al remoto (automáticamente jala la historia de los cambios que se hagan en la rama, en remoto).
- Se aceptan los cambios en GitHub.
- Se hace merge a master desde GitHub.

**Importante**: Cuando se modifica una rama, también se modifica el pull request.

Aporte creado por: David Behar

# 29 CREANDO UN FORK, CLON DE REPOSITORIO

Los ***forks* o bifurcaciones** son una característica única de GitHub en la que se crea una copia exacta del estado actual de un repositorio directamente en GitHub. Este repositorio podrá servir como otro origen y se podrá clonar (como cualquier otro repositorio). En pocas palabras, lo podremos utilizar como un nuevo repositorio git cualquiera

Un fork es como una bifurcación del repositorio completo. Comparte una historia en común con el original, pero de repente se bifurca y pueden aparecer varios cambios, ya que ambos proyectos podrán ser modificados en paralelo y para estar al día un colaborador tendrá que estar actualizando su *fork* con la información del original.

Al hacer un fork de un poryecto en GitHub, te conviertes en dueñ@ del repositorio fork, puedes trabajar en este con todos los permisos, pero es un repositorio completamente diferente que el original, teniendo solamente alguna historia en común (como crédito al creado o creadora original).

Los forks son importantes porque es la manera en la que funciona el open source, ya que, una persona puede no ser colaborador de un proyecto, pero puede contribuír al mismo, haciendo mejor software que pueda ser utilizado por cualquiera.

## Cómo se hace un fork remoto desde consola en GitHub

Al hacer un fork, GitHub sabe que se hizo el fork del proyecto, por lo que se le permite al colaborador hacer pull request desde su repositorio propio.

Cuando trabajas en un proyecto que existe en diferentes repositorios remotos (normalmente a causa de un fork), es muy probable que desees poder trabajar con ambos repositorios. Para esto, puedes generar un remoto adicional desde consola.

```
git remote add <nombre_del_remoto> <url_del_remoto>
git remote upstream https://github.com/freddier/hyperblog

```

Al crear un remoto adicional, podremos hacer pull desde el nuevo origen. En caso de tener permisos, podremos hacer fetch y push.

```
git pull <remoto> <rama>
git pull upstream master

```

Este pull nos traerá los cambios del remoto, por lo que se estará al día en el proyecto. El flujo de trabajo cambia, en adelante se estará trabajando haciendo *pull* desde el *upstream* y push al *origin* para pasar a hacer pull request.

```
git pull upstreammastergit push originmaster
```

Aporte creado por: David Behar

![Untitled](Git%20y%20GitHub%20a7cd841d61cc4e0bb4d3c27f90bb55c5/Untitled%2028.png)

# 30 Haciendo deplyment a un servidor

**Deploy** es el proceso que permite enviar al servidor uno o varios archivos. Este servidor puede ser de prueba, desarrollo o producción.

En el siguiente ejemplo veremos cómo se realiza el deployment de un documento en un servidor web básico.

## Pasos para hacer deployment en un servidor web:

- Entrar a la capeta de los archivos del servidor.
- Copiar link en *clone*, elegir entre HTTPS o SSH del repositorio a contribuir.En la carpeta deseada se clona el repositorio:

```
gitcloneurl
Deploy:

```

- Realizar cambios y *commit* en GitHub.
- Traer al Repositorio local las actualizacion para el servidor en la capeta de los archivos del servidor.

```
git pull ramaRemota main

```

Nota: Siempre se debe proteger el archivo .git. Dependiendo del software para el servidor web, existen diferentes maneras. La conexión entre GitHub y el servidor se puede realizar mediante: Travis (pago) o Jenkis (Open source).

Aporte creado por: Brayan Mamani, chedl

Para practicar de forma fácil pueden levantar un servidor local con python. Primero nos ubicamos en la carpeta del proyecto que queremos inicializar en el servidor y luego ejecutamos el comando según sea python2 o 3.

con Python 2:

```
python -m SimpleHTTPServer 8000
```

con Python 3.x:

```
python3 -m http.server 8000
```

El 8000 indica el puerto donde va a iniciar, entonces en el navegador vamos a 127.0.0.1:8000 y saldrá nuestro proyecto.

Se puede clonar el repo tranquilamente desde la terminal y para acceder, agrego en la barra de direcciones la ruta a la que quiero ir como hizo Freddy.

# 31 #HazmeUnPullRequest

1. hacer FORK de [hyperblog](https://github.com/freddier/hyperblog)
2. en blogpost.htmlDentro del ID “post” luego de “suscribete y dale like” agrega otra línea o párrafo con tu nombre o tu nombre de usuario en Platzi.
3. hacer add, commit, push
4. hacer un pull request
5. Esperar :v

#NuncaParesDeAprender

# 32 **Ignorar archivos en el repositorio con .gitignore**

No todos los archivos que agregas a un proyecto deberían ir a un repositorio. Por ejemplo, cuando tienes un archivo donde están tus contraseñas que comúnmente tienen la extensión `.env` o cuando te estás conectando a una base de datos; **son archivos que nadie debe ver**.

Por diversas razones, no todos los archivos que agregas a un proyecto deberían guardarse en un repositorio. Esto es porque hay archivos que no todo el mundo debería de ver, y hay archivos que al estar en el repositorio ralentizan el proceso de desarrollo (por ejemplo: los binary large objects, blob, que tardan en descargarse).

Para que no se suban estos archivos no deseados se puede crear un archivo con el nombre .gitignore en la raíz del repositorio con las reglas para los archivos que no se deberían subir: Aquí puedes ver la [sintaxis de los .gitignore](https://git-scm.com/docs/gitignore).

Las razones principales para tomar la decisión de no agregar un archivo a un repositorio son:

- Es un archivo con contraseñas (normalmente con la extensión .env)
- Es un blob (binary large object, objeto binario grande), mismos que son difíciles de gestionar en git.
- Son archivos que se generan corriendo comandos, por ejemplo la carpeta node_modules, que genera **npm** al correr el comando npm install

Aporte creado por: David Behar.

# 31 **Readme.md es una excelente práctica**

`README.md` es el lugar donde se explica de qué trata el proyecto, cómo utilizarlo y demás información que se considere que se deba conocer cualquier persona que vaya a trabajar de alguna forma con el proyecto..Los archivos README son escritos en un lenguaje llamado **markdown**, por eso la extensión .md, mismo que es un estándar de escritura en diversos sitios (como Platzi, Wikipedia y el mismo GitHub). Aquí puedes ver las [reglas de markdown](https://www.markdownguide.org/extended-syntax).

Los [README.md](http://readme.md/) pueden estar en todas las carpetas, pero el más importante es el que se encuentra en la raíz. Este documento ayuda a que los colaboradores sepan información relevante del proyecto, módulo o sección. Puedes crear cualquier archivo con la extensión .md pero solo los [README.md](http://readme.md/) los mostrará por defecto GitHub.

Aporte creado por: David Behar.

si quieren crear el **[README.md](http://readme.md/)** desde el mismo editor.**VSCODE** nos da una opción para poder visualizarlo.

para visualizarlo*1)* abrimos el archivo [README.md](http://readme.md/)*2)* damos click en la parte superior derecha en el siguiente icono

![https://i.imgur.com/Mjcz5ha.png](https://i.imgur.com/Mjcz5ha.png)

***Listo***

![https://i.imgur.com/P4NhQos.png](https://i.imgur.com/P4NhQos.png)

POSDATA:no es la gran cosa, pero nos ayuda en el caso de quieras hacer algo simple o no tengas internet.

### Lecturas recomendadas

[Editor.md - Open source online Markdown editor.
https://pandao.github.io/editor.md/en.html](https://pandao.github.io/editor.md/en.html)

# 33 **Tu sitio web público con GitHub Pages**

GitHub tiene un servicio de hosting gratis llamado **GitHub Pages**. Con él, puedes tener un repositorio alojado en GitHub y hacer que el contenido se muestre en la web en tiempo real.

Este es un sitio para nuestros proyectos donde lo único que tenemos que hacer es tener un repositorio alojado. En la página, podemos seguir las instrucciones para crear este repositorio

## Pasos para subir un repositorio a GitHub Pages

- Debemos tomar la llave SSH y hacer un `git clone #SSHexample` en mi computador local (Home).
- Luego, accederemos a la carpeta nueva que aparece en nuestra máquina local.
- Creamos un nuevo archivo que se llame index.html
- Guardamos los cambios, hacemos un `git pull` y seguido de esto un `git push` a `master`.
- Vamos a las opciones de *settings* de este repositorio y, en la parte de abajo, en la columna Github Pages, configuramos el *source* o fuente para que traiga la rama *master*
- Guardamos los cambios.

Después de esto, podremos ver nuestro trabajo en la web como si tuviéramos nuestro propio servidor.

Aporte creado por: Jhon Bangera.

### Archivos de la clase

index.html

### Lecturas recomendadas

[GitHub Pages | Websites for you and your projects, hosted directly from your GitHub repository. Just edit, push, and your changes are live.
https://pages.github.com/](https://pages.github.com/)

# 35 GIT Rebase: reorganizando el trabajo Realizado

**rebase:** reescribe la historia del repositorio, cambia la historia de donde comenzó la rama y **solo** debe ser usado de manera loca.

Rebase es el proceso de mover o combinar una secuencia de confirmaciones en una nueva confirmación base. La reorganización es muy útil y se visualiza fácilmente en el contexto de un flujo de trabajo de ramas de funciones. El proceso general se puede visualizar de la siguiente manera.

![https://static.platzi.com/media/user_upload/rebase1-45694a4e-3411-4785-8d6a-1545057ee1fc.jpg](https://static.platzi.com/media/user_upload/rebase1-45694a4e-3411-4785-8d6a-1545057ee1fc.jpg)

Para hacer un rebase en la rama feature de la rama master, correrías los siguientes comandos:

```
git checkout feature
git rebasemaster
```

Esto *trasplanta* la rama feature desde su locación actual hacia la punta de la rama master:

![https://static.platzi.com/media/user_upload/rebase2-3bcb1804-1167-4d2f-af90-c7fed7a7fd6c.jpg](https://static.platzi.com/media/user_upload/rebase2-3bcb1804-1167-4d2f-af90-c7fed7a7fd6c.jpg)

Ahora, falta fusionar la rama feature con la rama master

```
git checkoutmastergit rebase feature
# No reorganices el historial público

```

Nunca debes reorganizar las confirmaciones una vez que se hayan enviado a un repositorio público. La reorganización sustituiría las confirmaciones antiguas por las nuevas y parecería que esa parte del historial de tu proyecto se hubiera desvanecido de repente.

El comando ***rebase*** es **_una mala práctica, sobre todo en repositorios remotos. Se debe evitar su uso, pero para efectos de práctica te lo vamos a mostrar, para que hagas tus propios experimentos. Con `rebase` puedes recoger todos los cambios confirmados en una rama y ponerlos sobre otra.

```
# Cambiamos a la rama que queremos traer los cambios
git checkout experiment
# Aplicamos rebase para traer los cambios de la rama que queremos
git rebase master

```

Aporte creado por: Carlos Eduardo Diaz

# 36 **Git Stash: Guardar cambios en memoria y recuperarlos después**

El *stashed* nos sirve para guardar cambios para después, Es una lista de estados que nos guarda algunos cambios que hicimos en Staging para poder cambiar de rama sin perder el trabajo que todavía no guardamos en un commit

Ésto es especialmente útil porque hay veces que no se permite cambiar de rama, ésto porque tenemos cambios sin guardar, no siempre es un cambio lo suficientemente bueno como para hacer un commit, pero no queremos perder ese código en el que estuvimos trabajando.

El stashed nos permite cambiar de ramas, hacer cambios, trabajar en otras cosas y, más adelante, retomar el trabajo con los archivos que teníamos en Staging, pero que podemos recuperar, ya que los guardamos en el Stash.

## git stash

El comando git stash guarda el trabajo actual del Staging en una lista diseñada para ser temporal llamada Stash, para que pueda ser recuperado en el futuro.

Para agregar los cambios al stash se utiliza el comando:

```
git stash

```

Podemos poner un mensaje en el stash, para asi diferenciarlos en git stash list por si tenemos varios elementos en el stash. Ésto con:

```
git stash save "mensaje identificador del elemento del stashed"

```

## Obtener elelmentos del stash

El stashed se comporta como una [Stack](https://es.wikipedia.org/wiki/Pila_(inform%C3%A1tica)) de datos comportándose de manera tipo [LIFO](https://es.wikipedia.org/wiki/LIFO) (del inglés *Last In, First Out*, «último en entrar, primero en salir»), así podemos acceder al método pop.

El método **pop** recuperará y sacará de la lista el **último estado del stashed** y lo insertará en el **staging area**, por lo que es importante saber en qué *branch* te encuentras para poder recuperarlo, ya que el stash será **agnóstico a la rama o estado en el que te encuentres**. Siempre recuperará los cambios que hiciste en el lugar que lo llamas.

Para recuperar los últimos cambios desde el stash a tu staging area utiliza el comando:

```
git stashpop

```

Para aplicar los cambios de un stash específico y eliminarlo del stash:

```
git stashpopstash@{<num_stash>}

```

Para retomar los cambios de una posición específica del Stash puedes utilizar el comando:

```
git stash apply stash@{<num_stash>}

```

Donde el `<num_stash>` lo obtienes desden el `git stash list`

## Listado de elementos en el stash

Para ver la lista de cambios guardados en Stash y así poder recuperarlos o hacer algo con ellos podemos utilizar el comando:

```
git stash list

```

Retomar los cambios de una posición específica del Stash || Aplica los cambios de un stash específico

## Crear una rama con el stash

Para crear una rama y aplicar el stash más reciente podemos utilizar el comando

```
git stashbranch<nombre_de_la_rama>

```

Si deseas crear una rama y aplicar un stash específico (obtenido desde `git stash list`) puedes utilizar el comando:

```
git stashbranchnombre_de_rama stash@{<num_stash>}

```

Al utilizar estos comandos **crearás una rama** con el nombre `<nombre_de_la_rama>`, te pasarás a ella y tendrás el **stash especificado** en tu **staging area**.

## Eliminar elementos del stash

Para eliminar los cambios más recientes dentro del stash (el elemento 0), podemos utilizar el comando:

```
git stash drop

```

Pero si, en cambio, conoces el `índice` del stash que quieres borrar (mediante `git stash list`) puedes utilizar el comando:

```
git stash drop stash@{<num_stash>}

```

Donde el `<num_stash>` es el `índice` del cambio guardado.

Si, en cambio, deseas eliminar todos los elementos del stash, puedes utilizar:

```
git stash clear

```

## Consideraciones:

- El cambio más reciente (al crear un stash) **SIEMPRE** recibe el valor 0 y los que estaban antes aumentan su valor.
- Al crear un stash tomará los archivos que han sido modificados y eliminados. Para que tome un archivo creado es necesario agregarlo al Staging Area con git add [nombre_archivo] con la intención de que git tenga un seguimiento de ese archivo, o también utilizando el comando git stash -u (que guardará en el stash los archivos que no estén en el staging).
- Al aplicar un stash este no se elimina, es buena práctica eliminarlo.

Aporte creado por: David Behar.

# 37 **Git Clean: limpiar tu proyecto de archivos no deseados**

Mientras estamos trabajando en un repositorio podemos añadir archivos a él, que realmente no forma parte de nuestro directorio de trabajo, archivos que no se deberían de agregar al repositorio remoto.

El comando `clean` actúa en archivos sin seguimiento, este tipo de archivos son aquellos que se encuentran en el directorio de trabajo, pero que aún no se han añadido al índice de seguimiento de repositorio con el comando `add`.

```
$ git clean

```

La ejecución del comando predeterminado puede producir un error. La configuración global de Git obliga a usar la opción `force` con el comando para que sea efectivo. Se trata de un importante mecanismo de seguridad ya que este comando no se puede deshacer.

## Revisar que archivos no tienen seguimiento.

```
$ git clean --dry-run

```

## Eliminar los archivos listados de no seguimiento.

```
$ git clean -f

```

Git clean tiene muchísimas opciones adicionales, que puedes explorar al ver su [documentación oficial](https://git-scm.com/docs/git-clean).

![Untitled](Git%20y%20GitHub%20a7cd841d61cc4e0bb4d3c27f90bb55c5/Untitled%2029.png)

El parametro -d ayuda con el borrado de carpetas untracked. Por ejemplo: git clean -df hubiera borrado la carpeta “css - copia”

Git Clean tiene **un montón** de opciones.

Por ejemplo, si usas -**q** te mostrará solamente los errores que tuvo la ejecución, pero no los archivos que fueron borrados.

Si usas -**x** (En minúscula) borra las copias**incluyendo**

las que están dentro de un .gitignore

En cambio, si usas -**X** (En mayúscula) borra solamente los archivos ignorados por git

Hay muchas opciones más! Y las puedes ver en la **[documentación de Git Clean](https://git-scm.com/docs/git-clean)**

Git clean solo borra las cosas que puede indexar, no borrará por lo tanto lo incluído en gitignore.

# 38 **Git cherry-pick: traer commits viejos al head de un branch**

**Git Cherry-pick** es un comando que permite tomar uno o varios commits de otra rama o [branch](https://platzi.com/clases/1557-git-github/19947-que-es-un-branch-rama-y-como-funciona-un-merge-en-/) sin tener que hacer un merge completo. Así, gracias a cherry-pick, podríamos aplicar los commits relacionados con nuestra funcionalidad en la rama master sin necesidad de hacer un merge.

Para demostrar cómo utilizar git cherry-pick, supongamos que tenemos un repositorio con el siguiente estado de rama:

```
a -b - c - d   Master
         \
           e - f - g Feature

```

El uso de git cherry-pick es sencillo y se puede ejecutar de la siguiente manera:

```
git checkoutmaster

```

En este ejemplo, commitSha es una referencia de confirmación. Puedes encontrar una referencia de confirmación utilizando el comando git log. En este caso, imaginemos que queremos utilizar la confirmación ‘f’ en la rama master. Para ello, primero debemos asegurarnos de que estamos trabajando con esa rama master.

```
git cherry-pick f

```

Una vez ejecutado, el historial de Git se verá así:

```
a -b - c - d - f   Master
         \
           e - f - g Feature

```

La confirmación f se ha sido introducido con éxito en la rama de funcionalidad

## Atención

Cherry-pick **es una mala práctica** porque significa que estamos reconstruyendo la historia, **usa cherry-pick con sabiduría**. Si no sabes lo que estás haciendo, mejor evita emplear este comando.

Aporte creado por: Carlos Eduardo Diaz.

![Untitled](Git%20y%20GitHub%20a7cd841d61cc4e0bb4d3c27f90bb55c5/Untitled%2030.png)

# 39 **Git Reset y Reflog: úsese en caso de emergencia**

Git guarda todos los cambios aunque decidas borrarlos, al borrar un cambio lo que estás haciendo sólo es actualizar la punta del branch, para gestionar éstas puntas existe un mecanismo llamado registros de referencia o `reflogs`…La gestión de estos cambios es mediante los hash’es de referencia (o `ref`) que son apuntadores a los commits…Los recoges registran cuándo se actualizaron las referencias de Git en el repositorio local (sólo en el local), por lo que si deseas ver cómo has modificado la historia puedes utilizar el comando:

```
git reflog

```

Muchos comandos de Git aceptan un parámetro para especificar una referencia o “ref”, que es un puntero a una confirmación sobre todo los comandos:

- `git checkout` Puedes moverte sin realizar ningún cambio al commit exacto de la `ref`

  ```
  git checkout eff544f

  ```
- `git reset`: Hará que el último commit sea el pasado por la `ref`, usar este comando sólo si sabes exactamente qué estás haciendo

  ```
  git reset --hard eff544f # Perderá todolo quese encuentraen stagingyenel Working directoryyse moveráel headal commit eff544f
  git reset --soft eff544f # Te recuperará todos los cambios que tengas diferentesal commit eff544f, los agregaráal staging areay moveráel headal commit eff544f

  ```
- `git merge`: Puedes hacer merge de un commit en específico, funciona igual que con una branch, pero te hace el merge del estado específico del commit mandado

  ```
  git checkout master
  gitmerge eff544f # Fusionaráen un nuevo commitla historiade master con el momento específicoen elque vive

  ```

¿Qué pasa cuando todo se rompe y no sabemos qué está pasando? Con `git reset HashDelHEAD` nos devolveremos al estado en que el proyecto funcionaba.

- `git reset --soft HashDelHEAD` te mantiene lo que tengas en staging ahí.
- `git reset --hard HashDelHEAD` resetea absolutamente todo incluyendo lo que tengas en staging.

## Atención

`git reset` es una mala práctica, **no deberías usarlo en ningún momento**. Debe ser nuestro último recurso.

![Untitled](Git%20y%20GitHub%20a7cd841d61cc4e0bb4d3c27f90bb55c5/Untitled%2031.png)

# 40 Reconstruir commits en Git con amend

*Remendar* un commit con `amend` puede modificar el commit más reciente (enmendar) en la misma rama. Lo ejecutamos así:

```
gitadd -A # Para hacer uso de amend los archivos deben de estar en staging
git commit --amend # Remendar último commit

```

Este comando sirve para agregar archivos nuevos o actualizar el commit anterior y no generar commits innecesarios. También es una forma sencilla de **editar o agregar comentarios al commit anterior** porque abrirá la consola para editar este commit anterior.

## **Atención**

Usar `amend` es una **mala práctica**, sobre todo cuando ya se ha hecho **push o pull** al repositorio remoto. Al momento de hacer amend con algún `commit` que esté en remoto, va a generar un **conflicto** que se va a arreglar haciendo un `commit adicional` y se **perderá el beneficio** del amend.

Aporte creado por: David Behar.

![Untitled](Git%20y%20GitHub%20a7cd841d61cc4e0bb4d3c27f90bb55c5/Untitled%2032.png)

el `commit --amend` es muy util, pero hay que tener cuidado en algunos casos, como en el caso de que el commit que quieras enmendar lo hayas pusheado al repositorio remoto, entonces quieras enmendar un commit que esta en remoto.

Así como en el caso de `cherry-pick` y `rebase`, hay que usarlo con cuidado porque modificará la historia de tu repositorio.

Digamos que haces un cambio al archivo `a.txt` y haces un commit.

Luego subes ese commit al repositorio haciendo push.

Pero se te olvido agregar cambios a ese commit y quieres enmendarlo.

Haces `un git --amend` y en la historia de tu repositorio local, pareciera que no ha pasado nada: enmendaste tu commit.

Pero resulta que en el repositorio remoto eso no ha ocurrido, ese `git --amend` no tuvo lugar en el repositorio remoto, y al hacer `git status` te mostrará un error así:

```
Your branchand 'origin/master' have diverged,
and have 1and 1 different commitseach, respectively.
  (use "git pull" to mergethe remote branchinto yours)

```

y al momento de hacer push para sobreescribirlo, te aparecerá este error:

```
 ! [rejected]        master -> master (non-fast-forward)
error: failed to push some refs to 'git@github.com:luisxxor/hyperblog-1.git'
hint: Updates were rejected becausethe tipof your current branch is behind
hint: its remote counterpart. Integratethe remote changes (e.g.
hint: 'git pull ...')before pushing again.
hint: Seethe 'Note about fast-forwards'in 'git push --help'for details.

```

Y tendrás que hacer `git pull` para mergear los cambios de tu repositorio remoto y finalmente hacer push. Es decir, se puede hacer, pero sería contraproducente, porque la idea del amend era enmendar un sólo commit y no generar commits adicionales, pero el resultado de continuar haciendolo en éste caso es que tienes:

1. El primer commit
2. El commit enmendado
3. Y el commit del merge

**tl:dr**

Es una mala práctica enmendar un commit que ya ha sido pusheado al repositorio remoto.

Responder

**David Behar**

En pocas palabras, sólo usar ammend en local y no hacer push antes de remendar un commit

Creo que ahí lo menciona claramente y que ninguna de esas advertencias te saldrían si es que hubieras hecho un `git pull origin master` antes de hacer `git push origin master`

# 41 **Buscar en archivos y commits de Git con Grep y log**

A medida que nuestro proyecto en Git se hace más grande, vamos a querer buscar ciertas cosas.

Por ejemplo: ¿cuántas veces en nuestro proyecto utilizamos la palabra *color*?

Para buscar, empleamos el comando `git grep color` y nos buscará en todo el proyecto los archivos en donde está la palabra *color*.

- Con `git grep -n color` nos saldrá un output el cual nos dirá en qué línea está lo que estamos buscando.
- Con `git grep -c color` nos saldrá un output el cual nos dirá cuántas veces se repite esa palabra y en qué archivo.
- Si queremos buscar cuántas veces utilizamos un atributo de HTML lo hacemos con `git grep -c "<p>"`

git grep color -->use la palabra colorgit grep la --> donde use la palabra lagit grep -n color–> en que lineas use la palabra colorgit grep -n platzi --> en que lineas use la palabra platzigit grep -c la --> cuantas veces use la palabra lagit grep -c paltzi --> cuantas veces use la palabra platzigit grep -c “`<p>`”–> cuantas veces use la etiqueta `<p>`

git log-S “cabecera” --> cuantas veces use la palabra cabecera entodos los commits.

grep–> para los archivoslog --> para los commits.

![Untitled](Git%20y%20GitHub%20a7cd841d61cc4e0bb4d3c27f90bb55c5/Untitled%2033.png)

buscar palabras en los archivos en el branch actual

```
gitgrep "palabra a buscar"

```

mostrar la linea en la cual la pablara aparece en el archivo

```
gitgrep -n "palabra a buscar"

```

mostrar cuantas veces aparce la palabra en cada archivo

```
gitgrep -c "palabra a buscar"

```

buscar los commits en los cuales sale una palabra

```
git log -S "palabra a buscar"
```

Pueden probar lo aprendido en [learngitbranching](https://learngitbranching.js.org/) 👍

Responder

Pues lo **probé** y aún faltan algunas cosas

- no hay `git stash` por ejemplo, un comando escencial para cuando se hace bug-fixing

# 42 **Comandos y recursos colaborativos en Git y GitHub**

A continuación veremos una lista de comandos colaborativos para facilitar el trabajo remoto en GitHub:

- `git shortlog -sn`: muestra cuantos commit han hecho cada miembro del equipo.
- `git shortlog -sn --all`: muestra cuantos commit han hecho cada miembro del equipo, hasta los que han sido eliminados.
- `git shortlog -sn --all --no-merge`: muestra cuantos commit ha hecho cada miembro, quitando los eliminados sin los merges.
- `git blame ARCHIVO`: muestra quien hizo cada cosa línea por línea.
- `git COMANDO --help`:muestra como funciona el comando.
- `git blame ARCHIVO -Llinea_inicial,linea_final`: muestra quien hizo cada cosa línea por línea, indicándole desde qué línea ver. Ejemplo -L35,50.
- `git branch -r`: se muestran todas las ramas remotas.
- `git branch -a`: se muestran todas las ramas, tanto locales como remotas.

![Untitled](Git%20y%20GitHub%20a7cd841d61cc4e0bb4d3c27f90bb55c5/Untitled%2034.png)

**NOTAS CLASE:**

- **`git shortlog`**: Ver cuantos commits a hecho los miembros del equipo
- **`git shortlog -sn`**: Las personas que han hecho ciertos commits
- **`git shortlog -sn --all`**: Todos los commits (también los borrados)
- **`git shortlog -sn --all --no-merges`**: muestra las estadisticas de los comigs del repositorio donde estoy
- **`git config --global alias.stats “shortlog -sn --all --no-merges”`**: configura el comando “shortlog -sn --all --no-merges” en un Alias en las configuraciones globales de git del pc
- **`git blame -c blogpost.html`**: Muestra quien ha hecho cambios en dicho archivo identado
- **`git blame --help`**: Muestra en el navegador el uso del comando
- **`git blame archivo -L 35, 60 -c`**: Muestra quien escribio el codigo con informacion de la linea 35 a la 60, EJ: `git blame css/estilos.css -L 35, 60 -c`
- **`git branch -r`**: Muestra las Ramas remotas de GitHub
- **`git branch -a`**: Muestra todas las Ramas del repo y remotas de GitHub
