## Aprendiendo a usar Git y GitHub.

git init: se utiliza para iniciar nuestro repositorio.
git add ArchivoEjemplo.js: crea el archivo pero no lo guarda de forma definitiva, lo almacena en (Staging Area).
git commit -m "versión 1": aquí se generan cambios de "Staging Area" y con ( -m "") se deja un mensaje que nos sea útil.
git add .: Agrega los archivos actualizados al repositorio, pero únicamente en la carpeta que te encuentras.
git commit -m "Cambios v1": sirve para generar cambios sobre la versión antigua.
git status: sirve para revisar si has modificado o guardado los cambios hechos.
git log "archivo.txt": sirve para ver el historial del archivo.
git push: sirve para enviar cambios al repositorio remoto.
git pull: sirve para recibir cambios de repositorio remoto a local.

Ciclos de vida o estados de los archivos en Git
Cuando trabajamos con Git nuestros archivos pueden vivir y moverse entre 4 diferentes estados (cuando trabajamos remoto pueden ser más estados, pero lo estudiaremos más adelante)

Archivos Tracked: son los archivos que viven dentro de Git, no tienen cambios pendientes y sus últimas actualizaciones han sido guardadas en el repositorio gracias a los comandos git add y git commit.

Archivos Staged: son archivos en staging. Viven dentro de Git y hay registro de ellos por que han sido afectados por el comando git add, aunque no sus últimos cambios. Git ya sabe de la existencia de estos últimos cambios, pero todavía no han sido guardados definitivamente en el repositorio por que falta ejecutar el comando git commit.

Archivos Unstaged: entiendelos como archivos "Traked pero Unstaged". Son archivos que viven dentro de Git pero no han sido afectados por el comando git add ni mucho menos por git commit. Git tiene un registro de estos archivos, pero esta desactualizado, sus últimas versiones solo estan guardadas en su disco duro.

Archivos Untracked: son archivos que NO viven dentro de Git, solo en el disco duro. Nunca han sido afectados por git add, asi que Git no tiene registro de su existencia.

Recuerda que hay un caso muy raro donde los archivos tienen dos estados al mismo tiempo: Staged y Untracked. Esto pasa cuando guardas los cambios de un archivo en el área de Staging (con el comando git commit), pero antes de hacer commit para guardar los cambios en el repositorio haces nuevos cambios que todavía no han sido guardados en el área de Staging (en realidad, todo sigue funcionando igual pero es un poco divertido).

Comandos para mover archivos entre los estados de Git
git status: nos permite ver el estado de todos nuestros archivos y carpetas.

git add: nos ayuda a mover archivos del Untracked o Unstaged al estado Staged. Podemos usar git nombre del archivo o carpeta para añadir archivos y carpetas individuales o git add -a para mover todos los archivos de nuestro proyecto ( tanto Untrackeds como Unstageds).

git reset HEAD: nos ayuda a sacar los archivos del estado Staged para devolverlos a su estado anterior. Si los archivos venian de Unstaged, vuelven alli. Y lo mismo si venian de Untracked.

git commit: nos ayuda a mover archivos de Unstaged a Tracked. Esta es una ocasión especial, los archivos han sido guardados o actualizados en el repositorio. Git nos pedira que dejemos un mensaje para recordar los cambios que hicimos y podemos usar el argumento -m para describirlo ( git commit -m "mensaje").

git rm: este comando necesita algunos de los argumentos para poder ejecutarse correctamente:

git rm --cached: Mueve los archivos que le indiquemos al estado Untracked.

git rm --force: Elimina los archivos de Git y del disco duro. Git guarda el registro de la existencia de los archivos, por lo que podremos recuperarlos si es necesario (pero debemos usar comandos más avanzados).

Qué es un Branch y cómo funciona un Merge?
Checkout es para cambiar de rama. Sólo la crea con el modificador -b. Unir dos Ramas lo conocemos como Merge.

Estándar de equipos de desarrollo..

Rama Master o Main: va a producción.
Rama Development: se alojan las nuevas features, características y experimentos (para unirse al Máster cuando estén definitivamente listas).
Rama Hotfix: issues o errores se solucionan aquí para unirse al Master tan pronto sea posible.

Analizar cambios en los archivos de tu proyecto
git log: muestra la identificación de los commits.
git show: nos muestra los cambios que han existido sobre un archivo y es muy útil para detectar cuando se produjeron ciertos cambios, qué se rompió y cómo lo podemos solucionar. Pero podemos ser mas detallados.
git diff: nos muestra la diferencia entre una version y otra, no necesariamente todos los cambios desde la creación. (Gif diff commitA commitB).
