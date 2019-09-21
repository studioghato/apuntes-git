# Índice
1. [Documentación de Git](#documentacion-de-git)
   1. [Oficial (git-scm.com)](#oficial-git)
   1. [Enlaces de interés](#enlaces-de-interes)
1. [Introducción a Git](#introduccion-a-git)
   1. [Ayuda](#ayuda)
   1. [Cómo iniciar un repositorio](#como-iniciar-un-repositorio)
       1. [Qué contiene un repositorio Git](#que-contiene-un-repositorio-git)
       1. [Visualización del repositorio con interfaz gráfica (GUI)](#visualizacion-del-repositorio-con-interfaz-grafica-gui)
   1. [Cómo guarda Git toda la información](#como-guarda-git-toda-la-informacion)
   1. [Estados de los archivos](#estados-de-los-archivos)
       1. [STATUS CODES](#status-codes)
   1. [Configuración](#configuracion)
       1. [El archivo de configuración](#el-archivo-de-configuracion)
       1. [Cómo crear un usuario](#como-crear-un-usuario)
       1. [Cómo crear un alias de un comando extenso](#como-crear-un-alias-de-un-comando-extenso)
       1. [Cómo ocultar el mensaje de `CRLF`](#como-ocultar-el-mensaje-de-crlf)
       1. [Cómo cambiar el editor asociado a Git](#como-cambiar-el-editor-asociado-a-git)
       1. [Cómo guardar tus credenciales en la caché](#como-guardar-tus-credenciales-en-la-cache)
   1. [Aclaraciones sobre esta documentación](#aclaraciones-sobre-esta-documentacion)
   1. [Cómo renombrar un archivo](#como-renombrar-un-archivo)
   1. [Cómo eliminar un archivo](#como-eliminar-un-archivo)
   1. [Diferencias entre el operador `~` y `^`](#diferencias-entre-el-operador-~-y-^)
   1. [Diferencias entre el operador `..` y `...`](#diferencias-entre-el-operador-..-y-...)
   1. [Cómo buscar un string (cadena de texto)](#como-buscar-un-string-cadena-de-texto)
   1. [Cómo buscar un bug](#como-buscar-un-bug)
   1. [Cómo ver el estado del Working Directory](#como-ver-el-estado-del-working-directory)
1. [Staging Index](#staging-index)
   1. [Cómo añadir un archivo (*add*)](#como-anadir-un-archivo-add)
   1. [Cómo sacar un archivo (*unstage*)](#como-sacar-un-archivo-unstage)
   1. [Commit](#commit)
1. [Historia del repositorio](#historia-del-repositorio)
   1. [Log](#log)
   1. [Reflog](#reflog)
1. [Cambios](#cambios)
   1. [Significado de la cabecera de los resultados de los cambios](#significado-de-la-cabecera-de-los-resultados-de-los-cambios)
   1. [Cómo resaltar mejor los cambios](#como-resaltar-mejor-los-cambios)
   1. [Ver quién ha modificado un archivo](#ver-quien-ha-modificado-un-archivo)
   1. [Cómo ver cuántos archivos se han modificado del Working Directory y/o del Staging Index](#como-ver-cuantos-archivos-se-han-modificado-del-working-directory-y-o-del-staging-index)
   1. [Cómo ver el total de archivos que se van a añadir al siguiente commit](#como-ver-el-total-de-archivos-que-se-van-a-anadir-al-siguiente-commit)
   1. [Cómo ver los nuevos cambios o el contenido de una referencia y/o archivo desde la consola (`show`)](#como-ver-los-nuevos-cambios-o-el-contenido-de-una-referencia-y-o-archivo-desde-la-consola-show)
   1. [Cómo ver la evolución de los cambios de una referencia y/o archivo (`log -p`)](#como-ver-la-evolucion-de-los-cambios-de-una-referencia-y-o-archivo)
   1. [Comparar los cambios de un archivo entre dos ramas](#comparar-los-cambios-de-un-archivo-entre-dos-ramas)
   1. [Cambios entre árboles (Working Directory / Staging Index / HEAD del Repositorio Local)](#cambios-entre-arboles-working-directory-staging-index-head-del-repositorio-local)
       1. [Working Directory --- VS --- Staging Index](#working-directory-vs-staging-area)
       1. [Working Directory --- VS --- HEAD](#working-directory-vs-head)
       1. [Staging Index --- VS --- HEAD](#staging-area-vs-head)
   1. [Cambios entre commits](#cambios-entre-commits)
   1. [Cambios entre referencias (commits, ramas, etc...)](#cambios-entre-referencias-commits-ramas-etc)
   1. [Cambios de una rama desde que se hizo su fork](#cambios-de-una-rama-desde-que-se-hizo-su-fork)
   1. [RESUMEN de comandos `git diff`](#resumen-de-comandos-git-diff)
   1. [Revisar cambios de un/a compañero/a obtenidos de un repositorio remoto antes de hacer merge en tu rama](#revisar-cambios-de-un-a-companero-a-obtenidos-de-un-repositorio-remoto-antes-de-hacer-merge-en-tu-rama)
1. [Checkout](#checkout)
   1. [AVISO: Detached HEAD](#aviso-detached-head)
       1. [Cuándo y por qué aparece este aviso](#cuando-y-por-que-aparece-este-aviso)
       1. [SOLUCIÓN](#detached-head-solucion)
1. [Deshacer cambios](#deshacer-cambios)
   1. [Deshacer cambios de un archivo con CHECKOUT [PELIGROSO]](#deshacer-cambios-de-un-archivo-con-checkout-peligroso)
   1. [Deshacer cambios de un archivo con RESET  [N/D]](#deshacer-cambios-de-un-archivo-con-reset-no-se-puede)
   1. [Deshacer commits con RESET [PELIGROSO]](#deshacer-commits-con-reset-peligroso)
       1. [Efectos de cada tipo de reset](#efectos-de-cada-tipo-de-reset)
       1. [Cómo deshacer un `git reset --soft` o `--mixed`](#como-deshacer-un-git-reset-soft-o-mixed)
   1. [Deshacer commits con REVERT [RECOMENDADO]](#deshacer-commits-con-revert-recomendado)
       1. [Opciones de `git revert`](#opciones-de-git-revert)
   1. [Reset VS Checkout](#reset-vs-checkout)
       1. [Primera diferencia: efectos en el Working Directory](#primera-diferencia-efectos-en-el-working-directory)
       1. [Segunda diferencia: efectos en el HEAD](#segunda-diferencia-efectos-en-el-head)
       1. [TABLA RESUMEN: Alcance de RESET y CHECKOUT](#tabla-resumen-alcance-de-reset-y-checkout)
       1. [TABLA RESUMEN: Usos comunes y alcance de RESET, CHECKOUT y REVERT](#tabla-resumen-usos-comunes-y-alcance-de-reset-checkout-y-revert)
   1. [Reset VS Revert](#reset-vs-revert)
1. [Resumen de acciones no recomendadas porque seguro que perderás tu trabajo del Working Directory y/o commits del historial](#resumen-de-acciones-no-recomendadas-porque-seguro-que-perderas-tu-trabajo-del-working-directory-y-o-commits-del-historial)
1. [Ramas](#ramas)
   1. [Operaciones con ramas: `merge` y `rebase`](#operaciones-con-ramas-merge-y-rebase)
      1. [Tipos de merge](#tipos-de-merge)
      1. [MERGE VS REBASE](#merge-vs-rebase)
      1. [Opciones de `git rebase -i`](#opciones-de-git-rebase--i)
   1. [Squashing](#squashing)
      1. [Squashing con `git reset --soft`](#squashing-con-git-reset---soft)
      1. [Squashing con `git rebase -i`](#squashing-con-git-rebase--i)
   1. [Cherry-pick](#cherry-pick)
   1. [Cómo recuperar una rama eliminada](#como-recuperar-una-rama-eliminada)
   1. [Reescribir ramas (aplicar una acción en todos los commits del log)](#reescribir-ramas-aplicar-una-accion-en-todos-los-commits-del-log)
1. [Tags](#tags)
   1. [Cómo nombrar las versiones](#como-nombrar-las-versiones)
1. [Cómo guardar tu trabajo cuando está a medias y no quieres perderlo (`stash`)](#como-guardar-tu-trabajo-cuando-esta-a-medias-y-no-quieres-perderlo-stash)
1. [Clean](#clean)
1. [Prune](#prune)
1. [Trabajo con repositorios remotos](#trabajo-con-repositorios-remotos)
   1. [Clone](#clone)
   1. [Remote](#remote)
   1. [Fetch](#fetch)
       1. [Cómo actualizar la rama master local con todos los cambios que han surgido en el repositorio remoto](#como-actualizar-la-rama-master-local-con-todos-los-cambios-que-han-surgido-en-el-repositorio-remoto)
       1. [Tracking branches](#tracking-branches)
       1. [Cómo ver las tracking branches que están configuradas](#como-ver-las-tracking-branches-que-estan-configuradas)
           1. [Cómo crear una *tracking-branch* en el repositorio local](#como-crear-una-*tracking-branch*-en-el-repositorio-local)
   1. [Pull](#pull)
   1. [Push](#push)
1. [GitHub](#github)
   1. [Pull Request](#pull-request)
       1. [Opciones de merge](#opciones-de-merge)
   1. [Uso de referencias en comentarios](#uso-de-referencias-en-comentarios)
1. [EXTRAS](#extras)
   1. [Conversores online Markdown &rarr; HTML](#conversor-online-markdown-html)
   1. [Uso de la consola](#uso-de-la-consola)
       1. [Cómo proceder cuando un comando de Git nos muestra dos puntos `:` para realizar una acción](#como-proceder-cuando-un-comando-de-git-nos-muestra-dos-puntos)
       1. [Cómo mostrar directorios](#como-mostrar-directorios)
       1. [Cómo crear un archivo vacío](#como-crear-un-archivo-vacio)
       1. [Cómo escribir en un archivo (en Windows Bash)](#como-escribir-en-un-archivo-en-windows-bash)
           1. [Escribir una sola línea](#escribir-una-sola-linea)
           1. [Escribir múltiples líneas (opción 1)](#escribir-multiples-lineas-opcion-1)
           1. [Escribir múltiples líneas (opción 2)](#escribir-multiples-lineas-opcion-2)
       1. [Cómo despejar la consola](#como-despejar-la-consola)





# Documentación de Git <a name="documentacion-de-git"></a>


## Oficial (git-scm.com) <a name="oficial-git"></a>

- [DOC Home](https://git-scm.com/doc)

- [DOC Reference](https://git-scm.com/docs)


## Enlaces de interés <a name="enlaces-de-interes"></a>

- [BitBucket Atlassian](https://es.atlassian.com/git/tutorials)

- [GitHub Cheat Sheet (PDF)](https://github.github.com/training-kit/downloads/github-git-cheat-sheet.pdf)

- [Interactive Git Cheat Sheet](http://ndpsoftware.com/git-cheatsheet.html)

- [How to solve a mess (PNG)](http://justinhileman.info/article/git-pretty/git-pretty.png)

- [2.2 Git Basics - Recording Changes to the Repository](https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository)

- [Guía para principiantes: "git - the simple guide"](https://rogerdudler.github.io/git-guide/)


# Introducción a Git <a name="introduccion-a-git"></a>


## Ayuda <a name="ayuda"></a>

```php
git --version       //
git help            //
git help <command>  //
```


## Cómo iniciar un repositorio <a name="como-iniciar-un-repositorio"></a>

```php
git init  //
```
- Al ejecutar el comando `git init` se crea un nuevo respositorio vacío con una única rama: `master`, con el HEAD indicando la punta de la rama. HEAD (por lo general) es el último commit de la rama actual en la que te encuentras.

- Si ya existe un repositorio lo reinicia, pero en ningún caso lo sobreescribe. **Es 100% seguro**.

- Inicia el Working Directory (WD).

- Toda la información del repositorio se encuentra en el directorio oculto `.git`. Este directorio está oculto por seguridad, para evitar que en el caso de que se eliminen accidentalmente todos los archivos del directorio del proyecto, también se pierda la historia del repositorio. De este modo todavía será posible recuperar los archivos y todo el historial de cambios del proyecto.


### Qué contiene un repositorio Git <a name="que-contiene-un-repositorio-git"></a>

| STASH | WORKING DIRECTORY | STAGING INDEX | LOCAL REPOSITORY | REMOTE REMOPOSITORY |
| ----- | ----------------- | ------------- | ---------------- | ------------ |
| Trabajo/s en proceso guardado/s. Puede llegar a contener archivos `tracked`, `untracked` e `ignored`. | Estado actual del directorio (todo su contenido cambia en función de la referencia en la que te encuentres). Puede llegar a contener archivos tracked, untracked e ignored. | Archivos del Working Directory en seguimiento con nuevos cambios locales preparados para el siguiente commit. **¡IMPORTANTE! Actualizar el Staging Index antes de hacer el `commit`**, sino los archivos se subirán al repositorio en el estado en el que fueron añadidos al Staging Index (*snapshot* inicial) y no en su versión más reciente). | Contiene el historial de todas las ramas (*`branches`*) con todos sus `commits`, además de los `tags` y los `stashes` (los `stashes` solo son locales). | Contiene el historial de todas las ramas que se hayan ido subiendo, además de los tags (¡IMPORTANTE! Se tienen que subir manualmente con `git push --tags` o individualmente con `git push <remote> <tag>`). No puede contener `stashes`. |
| **COMANDOS APLICABLES A CADA COLUMNA** |
| Consultarlos en esta [guía visual e interactiva](https://ndpsoftware.com/git-cheatsheet.html) (español) |
***


### Visualización del repositorio con interfaz gráfica (GUI) <a name="visualizacion-del-repositorio-con-interfaz-grafica-gui"></a>

```php
gitk  // Abre la aplicación GUI
```


## Cómo guarda Git toda la información <a name="como-guarda-git-toda-la-informacion"></a>

- The *workspace* is the **directory tree** of (source) files that you see and edit.

- The **index** is a single, large, binary file in <baseOfRepo>/.git/index, which lists all files in the current branch, their sha1 checksums, time stamps and the file name -- it is not another directory with a copy of files in it.

- The **local repository** is a hidden directory (.git) including an objects directory containing all versions of every file in the repo (local branches and copies of remote branches) as a compressed "blob" file.

Don't think of the four 'disks' represented in the image above as separate copies of the repo files.

(Fuente: https://stackoverflow.com/a/3690796)


## Estados de los archivos <a name="estados-de-los-archivos"></a>

- Cada archivo del Working Directory puede estar en dos estados:
    - **TRACKED** = son los archivos de los que Git tiene conocimiento, bien porque (1) están en el Staging Index o (2) porque estaban en el último *snapshot* (commit) y, por lo tanto, no es necesario que estén en el STAGE para saber si hay diferencias; porque comparándolos con el último COMMIT ya lo sabe. Pero sí que es necesario volvera a añadir al STAGE los archivos que queramos preparar para el siguiente COMMIT. El caso 2 es el de cuando recién clonas un repositorio.

        Los TRACKED FILES Pueden estar como:
            - **unmodified**
            - **modified**
            - **staged**

    - **UNTRACKED** = todo lo demás, es decir, cualquier archivo de tu Working Directory que...
        - no estuviera en el último *snapshot*
        - que no esté en el Staging Index (status code: `??` en color rojo).

- Cuando CLONAS un repositorio (`git clone`) TODOS LOS ARCHIVOS están en estado TRACKED-UNMODIFIED, porque Git solo ha hecho un CHECKOUT de ellos y tú todavía no has editado ningún archivo. Es decir, están *tracked* porque el repositorio ya contiene un commit donde se añadieron, y Git puede comparar tu Working Directory con ese último commit para saber si hay diferencias. Pero si haces `git status` puedes comprobar que no están en el Staging Index, porque por seguridad Git te obliga a añadir manualmente los archivos que quieres incluir en el siguiente commit, así se evita incluir más archivos de la cuenta.

- Cuando haces COMMIT todos los archivos del STAGE se quitan de ahí y en el Working Directory se les asigna el estado de UNMODIFIED de nuevo, porque esos últimos cambios pasan a ser la nueva referencia para saber si se han producido nuevas modificaciones. Por eso al hacer un `git status -sb` muestra el mensaje `"nothing to commit, working tree clean"`, porque ahora no hay nada en el `stage` ya que se empieza de nuevo.

### STATUS CODES <a name="status-codes"></a>

```php
XY
X   // Status of the Staging Index
 Y  // Status of the Working Tree (Working Directory)
```

| Char | Meaning |
| ---- | ------- |
|`''`|Unmodified|
|`M`|Modified|
|`A`|Added|
|`D`|Deleted|
|`R`|Renamed|
|`C`|Copied|
|`U`|Updated but unmerged|
|`??`|Untracked|
|`!!`|Ignored|

[More info about `git-status` codes](https://git-scm.com/docs/git-status#_short_format)


## Configuración <a name="configuracion"></a>

- Usar `git config` para ver la configuración del repositorio actual.

- Usar `git config --global` para configurar el nombre de usuario, email, editor y otras opciones una sola vez para todo un mismo ordenador.


### El archivo de configuración <a name="el-archivo-de-configuracion"></a>

```php
git config --global -e          // Editar archivo de configuración
git config --global -l          // Leer archivo de configuración (más seguro)
```

Ubicación del archivo de configuración:

```php
git config --list --show-origin // Ubicación archivo config global

// C:/Users/Your-User-Name/.gitconfig
```


### Cómo crear un usuario <a name="como-crear-un-usuario"></a>

```php
git config --global user.name "<name>"    // Crear usuario de Git
git config --global user.email "<email>"  // Asignar email al usuario de Git
```


### Cómo crear un alias de un comando extenso <a name="como-crear-un-alias-de-un-comando-extenso"></a>

```php
git config --global alias.<your-alias> "<real-command-without-git>"       // Crear alias

git config --global alias.s "status -s -b"                                // Alias del status
git config --global alias.lg "log --oneline --decorate --all --graph"     // Alias del log con el árbol
git config --global alias.lgp "log --pretty=format:'%h - %an, %ar : %s'"  // Alias del log con "Hash + AuthorName + Author date, relative + Subject". Ejemplo: ca82a6d - Scott Chacon, 6 years ago : changed the version number
```


### Cómo ocultar el mensaje de `CRLF` <a name="como-ocultar-el-mensaje-de-crlf"></a>

```php
git config core.autocrlf true  // Evitar que aparezca de nuevo el mensaje relativo a CRLF.
```


### Cómo cambiar el editor asociado a Git <a name="como-cambiar-el-editor-asociado-a-git"></a>

```php
git config --global core.editor <editor>  // Cambiar el editor asociado a Git
```


### Cómo guardar tus credenciales en la caché <a name="como-guardar-tus-credenciales-en-la-cache"></a>

```php
git config --global credential.helper cache  // Permite almacenar temporalmente tus credenciales en la caché de Git durante unos minutos para no tener que introducir tu usuario y contraseña cada vez que quieras hacer un `git push`.
```

Más información en [Git Tools - Credential Storage](https://git-scm.com/book/en/v2/Git-Tools-Credential-Storage#_credential_caching).


## Aclaraciones sobre esta documentación <a name="aclaraciones-sobre-esta-documentacion"></a>

- **Derechos de autor y fuentes consultadas:**

  La gran mayoría del contenido ha sido redactado íntegramente por mí. Pero esta documentación también contiene:
  
  - Fragmentos que he traducido directamente de otras fuentes por considerarlos imprescindibles para comprender mejor la materia por lo bien explicados que estaban.
  
  - Pequeños fragmentos copiados íntegramente y/o imágenes de otras fuentes.
  
  En todos los apartados que he consultado y/o usado de algún modo (parcial o totalmente) recursos para desarrollar su contenido, he citado la fuente original.

  He usado dichas fuentes estrictamente con fines educativos. Pero si eres el autor de alguna de estas fuentes y quieres que retire el contenido que te pertenece, por favor, ponte en contacto conmigo y lo eliminaré al instante.

- **Referencias en comandos:**
  
  Cuando un comando acepta una referencia `<ref>`, quiere decir que se puede indicar cualquiera de estos tipos:

  - SHA-1 (commit hash)
  - branch-name
  - HEAD
  - HEAD~ (the parent of HEAD)
  - HEAD^
  - HEAD~3
  - tag
  - stash
  - ...


## Cómo renombrar un archivo <a name="como-renombrar-un-archivo"></a>

Hay tres maneras de hacerlo:

- **Renombrarlo desde el editor de texto**
  
  Git lo detecta en el Working Directory con el estado `deleted`, y cree que hay un nuevo archivo (estado `??`), que es el que tiene el nuevo nombre. Al hacer un `git add -u` (actualizar el Staging Index) entiende que se ha renombrado y lo añade al Staging Index con el estado `rename`.

- **Renombrarlo desde la consola**
  
  Si lo haces con el comando nativo `mv` de la consola, luego es necesario ejecutar 2 comandos de Git. Ejemplo:

  ```php
  mv README.md README  // git mv <nombre-old> <nombre-new>
  git rm README.md
  git add README
  ```

- **Renombrarlo desde Git (opción recomendada)**
  
  Si lo haces con el comando de Git `git mv <old-name> <new-name>`, Git ejecuta los tres comandos de la opción anterior en uno solo y lo añade al Staging Index en estado `renamed`.

En todos los casos, en el siguiente commit que realizas Git tiene en cuenta el renombramiento.


## Cómo eliminar un archivo <a name="como-eliminar-un-archivo"></a>

Hay tres maneras de hacerlo:

- **Eliminarlo desde el editor de texto**
  
  Git lo detecta en el Working Directory con el estado de `deleted`. Al hacer un `git add -u` lo añade al Staging Index en estado `deleted`.

- **Eliminarlo desde la consola**
  
  Si lo haces con el comando nativo `rm` de la consola, Git lo detecta en el Working Directory con el estado de `deleted`. Al hacer un `git rm <file>` lo añade al Staging Index en estado `deleted`.

- **Eliminarlo desde Git (opción recomendada)**
  
  Al hacer un `git rm <file | list-of-files | directory | glob pattern>` lo/s añade directamente al Staging Index en estado `deleted`. Es un *shortcut*, porque actualiza tanto el Working Directory como el Staging Index.
  
  ```php
  git rm <file | list-of-files | directory | glob pattern>             // Eliminar un archivo en seguimiento.
  git rm <file | list-of-files | directory | glob pattern> --cached    // Mantiene el archivo (que tiene cambios respecto al último commit) en el Working Directory y solo lo elimina del Staging Index para que nunca más le haga seguimiento.
  git rm <file | list-of-files | directory | glob pattern> -f|--force  // Fuerza la eliminación de un archivo en seguimiento (que tiene cambios respecto al último commit) tanto del Working Directory como del Staging Index.

  git commit  // Los archivos preparados para ser eliminados solo se eliminan en el siguiente commit.
  ```
  
  Si el archivo que quieres eliminar lo has modificado en el Working Directory desde el último commit y/o ya lo has añadido al Staging Index, `git rm` lanza un error (*`error: the following file has local modifications:`*), porque Git tiene un mecanismo de seguridad que impide eliminar archivos que no coinciden con el estado del último commit, ya que le sería imposible recuperar esos cambios que nunca han sido guardados en un *snapshot*.

  Ante esta situación te da dos opciones:

  - Mantener el archivo en el Working Directory y solo eliminarlo del Staging Index para que nunca más le haga seguimiento:
  
    ```php
    git rm --cached <file> // Mantiene el archivo indicado en el Working Directory y solo lo elimina del Staging Index para que nunca más le haga seguimiento.
    ```

  - Forzar la eliminación del archivo tanto del Working Directory como del Staging Index:

    ```php
    git rm -f|--force <file> // Fuerza la eliminación del archivo indicado tanto del Working Directory como del Staging Index:
    ```

  > **IMPORTANTE:**
  > 
  > `git rm` is actually a convenience command that combines the standard shell `rm` and `git add` to remove a file from the working directory and promote that removal to the staging index. **A repository can get into a cumbersome state in the event that several files have been removed using only the standard shell rm command.**
  > 
  > If intentions are to record all the explicitly removed files as part of the next commit, `git commit -a` will add all the removal events to the staging index in preparation of the next commit.
  > 
  > If however, intentions are to persistently remove the files that were removed with the shell `rm`, use the following command:
  > 
  > `git diff --name-only --diff-filter=D -z | xargs -0 git rm --cached`
  > 
  > This command will generate a list of the removed files from the working directory and pipe that list to `git rm --cached` which will update the staging index.

En todos los casos, en el siguiente commit que realizas Git no incluye el/los archivos eliminado/s en el *snapshot*, entonces ya deja de hacerle/s seguimiento; y además lo/s elimina del Working Directory para que no lo/s veas más.

Como Git **no elimina el/los archivo/s hasta que haces un commit**, siempre **puedes deshacer esta acción** con `git reset HEAD` o `git checkout .`. Esto devolverá el Working Directory y el Staging Index al estado del último commit. **IMPORTANTE:** si has hecho cambios en otros archivos deberías guardarlos antes en un [**stash**](#como-guardar-tu-trabajo-cuando-esta-a-medias-y-no-quieres-perderlo-stash) para no perderlos. O si no quieres hacer un *stash*, entonces ejecuta el comando `git reset HEAD <file-name>` o `git checkout HEAD -- <file-name>` para recuperar los archivos concretos sin perder los últimos cambios de los demás archivos del Working Directory.


## Diferencias entre el operador `~` y `^` <a name="diferencias-entre-el-operador-~-y-^"></a>

Para moverte en el tiempo hacia atrás hay dos opciones: `^` y `~`; que se puedan usar tomando como referencia el `HEAD` o el código SHA-1 de cualquier commit, como en estos  ejemplos:

```php
HEAD~2
c5f567~2

HEAD^2
c5f567^2
```

- Cuando se trata de **moverte solo una posición, son equivalentes**:

  ```php
  HEAD^ == HEAD^1
  HEAD~ == HEAD~1
  HEAD^ == HEAD~
  ```

- Cuando se trata de **moverte más de una posición, son diferentes**:

   - Con `~` te mueves linealmente siempre.
   - Con `^` te mueves por los padres de un commit que es el resultado de un merge entre dos o más ramas.
      - Es decir si tres ramas se unen y el HEAD es el commit resultante:
          - HEAD^1 = su primer padre
          - HEAD^2 = su segundo padre
          - HEAD^3 = su tercer padre
          - etc...
  
  ```php
  HEAD~3 == HEAD^^^
  HEAD~3 != HEAD^3
  ```

  


------------
**Rules of thumb**

- Use `~` most of the time — to go back a number of generations, usually what you want
- Use `^` on merge commits — because they have two or more (immediate) parents

**Mnemonics:**

- Tilde `~` is almost linear in appearance and wants to go backward in a straight line
- Caret `^` suggests an interesting segment of a tree or a fork in the road

(Fuente: https://stackoverflow.com/questions/2221658/whats-the-difference-between-head-and-head-in-git)

------------
Both `~` and `^` on their own refer to the parent of the commit (`~~` and `^^` both refer to the grandparent commit, etc.) But they differ in meaning when they are used with numbers:

`~2` means up two levels in the hierarchy, via the first parent if a commit has more than one parent

`^2` means the second parent where a commit has more than one parent (i.e. because it's a merge)

These can be combined, so `HEAD~2^3` means HEAD's grandparent commit's third parent commit.

(Fuente: https://stackoverflow.com/questions/2221658/whats-the-difference-between-head-and-head-in-git)

------------
The difference between HEAD^ and HEAD~ is well described by the illustration (by Jon Loeliger) found on http://www.kernel.org/pub/software/scm/git/docs/git-rev-parse.html.

This documentation can be a bit obscure to beginners so I've reproduced that illustration below:

```php
G   H   I   J
 \ /     \ /
  D   E   F
   \  |  / \
    \ | /   |
     \|/    |
      B     C
       \   /
        \ /
         A
A =      = A^0
B = A^   = A^1     = A~1
C = A^2
D = A^^  = A^1^1   = A~2
E = B^2  = A^^2
F = B^3  = A^^3
G = A^^^ = A^1^1^1 = A~3
H = D^2  = B^^2    = A^^^2  = A~2^2
I = F^   = B^3^    = A^^3^
J = F^2  = B^3^2   = A^^3^2
```

(Fuente: https://stackoverflow.com/questions/2221658/whats-the-difference-between-head-and-head-in-git)


## Diferencias entre el operador `..` y `...` <a name="diferencias-entre-el-operador-..-y-..."></a>

**Tienen diferente significado según si se usan con el comando `git diff` y/o con `git log`.**

- **`git diff <ref-A> [..|...|' '] <ref-B>`**
  - `..`
    
    Si las dos referencias son ramas, compara las dos puntas de ambas ramas. Es decir, muestra las diferencias de <ref-B> respecto a <ref-A>.

    Es lo mismo que usar un espacio `' '`.

  - `...`
    
    Si las dos referencias son ramas, la primera referencia se cambia y pasa a ser la referencia del último commit que comparten ambas ramas, es decir, en el que se bifurcan (*fork*), conocido como "*merge base*". La segunda referencia se mantiene intacta.
    
    Te permite ver todo lo que la rama B ha incorporado desde aquél punto, ignorando todo lo que haya podido avanzar la rama A desde esa misma referencia.

    ![git diff](http://tpscash.github.io/images/posts/git/git-diff-help.png)

  - `' '` (espacio)
    
    Es lo mismo que usar los dos puntos `..`.
    
- **`git log <ref-A> [..|...|' '] <ref-B>`**
  
  - `..`
    
    Muestra todos los commits de `<ref-B>` que no están en `<ref-A>`.

  - `...`
    
    Muestra todos los commits de `<ref-A>` y de `<ref-B>`, excepto los que tienen en común.

  - `' '` (espacio)
    
    Muestra todos los commits de `<ref-A>` y de `<ref-B>`, y los que tienen en común.


  > [What are the Diffferences Between Double Dot and Triple Dot in Git](http://tpscash.github.io/2016/11/02/what-are-the-differences-between-double-dot-and-triple-dot-in-git/)
  > 
  > A common source of confusion here is that `..` and `...` mean subtly different things when used in a command such as `git log` that expects a set of commits as one or more arguments. (These commands all end up using `git rev-list` to parse a list of commits from their arguments).
  > 
  > The meaning of `..` and `...` for `git log` can be shown graphically as below:
  > 
  > ![git rev-list (git log)](http://tpscash.github.io/images/posts/git/git-log-help.png)

(Fuente: http://tpscash.github.io/2016/11/02/what-are-the-differences-between-double-dot-and-triple-dot-in-git/)


## Cómo buscar un string (cadena de texto) <a name="como-buscar-un-string-cadena-de-texto"></a>

```php
git grep "<string>" <ref>   // Busca la cadena de texto <string> en la referencia indicada.
git grep "function" v2.5.0  // Busca la cadena de texto "function" en el tag de referencia "v2.5.0".
```


## Cómo buscar un bug <a name="como-buscar-un-bug"></a>

*PENDIENTE DESARROLLAR*

```php
// Example
$ git bisect start
$ git bisect bad                 # Current version is bad
$ git bisect good v2.6.13-rc2    # v2.6.13-rc2 is known to be good

// Full example at: https://git-scm.com/docs/git-bisect#_basic_bisect_commands_start_bad_good
```

(Fuente: https://git-scm.com/docs/git-bisect)


## Cómo ver el estado del Working Directory <a name="como-ver-el-estado-del-working-directory"></a>

- `git status` muestra dos cosas:
   
   - El estado de los archivos, tanto de los que están en seguimiento como de los que no.
   - E indica qué archivos están en el Staging Index (y en qué estado) para ser incluídos en el siguiente *snapshot* (commit).

- `git status` no reconoce un nuevo directorio hasta que no contiene algún archivo.

- `git status` muestra el estado de un archivo en rojo cuando no está en seguimiento (`??`) y/o cuando está en seguimiento y ha sido modificado (`M`).

- `git status` muestra paths con diferencias entre:

   1. Staging Index File (Stage) VS Current HEAD Commit
   2. Working Directory VS Staging Index File (Stage)
   3. Working Directory not tracked by Git because of .gitignore

[Más información sobre `git-status`](https://git-scm.com/docs/git-status)

```php
git status        //
git status -s     // -s = Short
git status -b     // -b = Branches
git status -s -b  //
```
[Ver todos los códigos de estado](#status-codes)


# Staging Index <a name="staging-index"></a>


## Cómo añadir un archivo (*add*) <a name="como-anadir-un-archivo-add"></a>

```php
git add .                           // Añade al Staging Index todos los archivos del Working Directory (el punto indica el directorio actual)
git add -- .                        // Añade al Staging Index todos los archivos del Working Directory (el punto indica el directorio actual)
git add -A                          // Añade al Staging Index todos los archivos del Working Directory (-A = All)
git add -u                          // Actualiza todos los archivos del Staging Index (-u = update). Pasan del estado "AM <nombre>" al "A  <nombre>". Imprescindible ejecutarlo antes de un commit y/o de crear un stash.
git add <dir>/                      //
git add <file-name-with-extension>  //
git add *.<extension>               //
git add *.html                      //
git add <file-name-1-with-extension> <file-name-2-with-extension> ... <file-name-N-with-extension>  //
git add -i                          // Inicia una sesión interactiva de Staging para permitirte elegir qué accion realizar con cada archivo que está en seguimiento.
git add -p                          // Inicia una sesión interactiva de Staging para permitirte seleccionar las partes de código concretas que quieres añadir al Index. This will present you with a chunk of changes and prompt you for a command. Use "y" to stage the chunk, "n" to ignore the chunk, "s" to split it into smaller chunks, "e" to manually edit the chunk, and "q" to exit.
```

Para **ver con detalle qué versión de un archivo está en el Staging Index** podemos ejecutar el siguiente comando `git ls-files -s`:

```php
git ls-files -s  // Muestra el hash de cada archivo que está en el Staging Index. De este modo puedes analizar perfectamente cómo se actualiza parcialmente el Staging Index cuando ejecutas `git reset <ref> <file>`, por ejemplo.
```


## Cómo sacar un archivo (*unstage*) <a name="como-sacar-un-archivo-unstage"></a>

Cuando trabajamos con [`git reset` a nivel de commits](#deshacer-commits-con-reset-peligroso), se hace apuntar el HEAD a la referencia indicada de commit. **Pero al indicar el *path* de un archivo, internamente no se realiza este primer paso del reset porque no se puede**.

> Esto es lógico, porque el HEAD solo es un puntero, y no puede apuntar a la vez a una parte de un commit por un lado, y a otro commit por otro lado.

Pero el Staging Index y el Working Directory sí que pueden ser parcialmente actualizados, con lo cual el reset sí que puede hacer los pasos 2 y 3 (actualizar esos árboles). En este aspecto hay que tener en cuenta que como por defecto el reset se comporta como `--mixed`, si haces `git reset file.txt` se detiene al finalizar el paso 2 (actualizar el Staging Index). El efecto es el de haber hecho un *unstage*, porque copia el estado del archivo del HEAD al Staging Index, quedando los 3 árboles como si todavía no hubieras propuesto tus cambios locales de ese archivo para el siguiente *snapshot* después de haber hecho el último commit:

| WORKING DIRECTORY | INDEX | HEAD |
| ----------------- | ----- | ---- |
| `file(v2).txt` | `file(v1).txt` | `<---` `file(v1).txt` |

Así que cuando se hace un **unstage** no se está "quitando" del Staging Index el archivo que previamente has añadido con `git add` (aunque así lo digamos comunmente), porque entonces no habría ninguna versión de referencia de ese archivo en el Staging Index con la que poder comparar si la versión del Working Directory tiene nuevos cambios.

Lo que realmente sucede es que Git copia la referencia del archivo del HEAD al Staging Index para que vuelva a corresponder con el estado del último commit. Es decir, es como si no hubieras propuesto tus últimos cambios para el siguiente commit porque vuelve a dejar el registro de ese archivo en el Staging Index como si acabaras de hacer el último commit.

De modo que desde que nuestro repositorio tiene como mínimo un commit, en el Staging Index siempre va a haber la referencia de una versión determinada por cada archivo. Normalmente esta referencia será la versión del HEAD (último commit), pero [también puede ser la de otro commit](#hacer-reset-seleccionando-archivos-que-pertenecen-a-otro-commit).

Entender bien cómo actúa Git cuando decimos que "quita archivos del Staging Index" es imprescindible para comprender perfectamente qué hace `git reset`.

**Hacer un `git reset` de este tipo (o, lo que es lo mismo, `git reset --mixed`) es seguro porque el Working Directory permanece intacto, siempre y cuando no uses la opción "--hard", en cuyo caso sí eliminaría los cambios locales del Working Directory y no los podrías recuperar.**

```php
git reset <file>               // Copia el archivo del HEAD al Staging Index para hacer un "unstage". Es como si todavía no hubieras propuesto tus cambios de ese archivo para el siguiente *snapshot* después de haber hecho el último commit.
// - or -
git reset HEAD <file>
// - or -
git reset --mixed HEAD <file>

// Ejemplo
git reset *.xml                // Copia todos los archivos XML del HEAD al Staging Index para hacerles un "unstage".
```

**También podemos hacer reset seleccionando archivos que pertenecen a otro commit.** <a name="hacer-reset-seleccionando-archivos-que-pertenecen-a-otro-commit"></a>

La modalidad de reset `git reset <ref> <file>` nos permite incluir en el siguiente commit uno de los archivos actuales en seguimiento pero en su versión anterior (la que queramos) en lugar de la actual; y aún así no perder su estado actual para los próximos commits, porque como ya hemos dicho más arriba, `git reset --mixed` no modifica el Working Directory.

Si después de ejecutar el comando anterior nos arrepentimos y queremos volver a tener en el Staging Index la referencia de la versión del archivo del HEAD (tal como estábamos antes), basta con ejecutar el comando `git reset <file>`, porque este comando siempre recupera la referencia del archivo del HEAD de la rama actual. Esto funcionará siempre y cuando no hayamos hecho un commit después de haber ejecutado el `git reset <ref> <file>`.

```php
git reset <ref> <file>     // Copia el archivo <file> ("file.txt", por ejemplo) en la versión de la referencia indicada (se presupone anterior al commit en el que te encuentras) en el Staging Index (tu HEAD y Working Directory siguen idénticos porque por defecto un reset se comporta como "--mixed"). Te permite incorporar al siguiente commit un archivo en una de sus versiones anteriores en lugar de comitear su estado actual, mientras que el resto de tus archivos del Staging Index corresponden con el estado en el que estaban antes de hacer el reset. De modo que esa versión anterior vuelve volver a formar parte de un nuevo commit, pero tu versión actual del archivo no la pierdes porque sigue estando intacta en el Working Directory y la podrás incluir en el siguiente commit (será el posterior al commit que vuelve a contiener la versión antigua, en el caso de que hayas realizado dicho commit).
git reset <ref> README.md
```


## Commit <a name="commit"></a>

```php
git commit                               // Commit con mensaje multilínea
git commit -m "<mensaje>"                // Commit con mensaje de una línea.
git commit -am "<mensaje>"               // Commit con mensaje de una línea, pero antes añade al Staging Index todos (y solo) los archivos que ya están en seguimiento, y/o actualiza los que ya estuvieran en el Staging Index para incorporar todos sus cambios. IMPORTANTE: Los archivos nuevos no los añade porque están "untracked".
git commit --amend                       // Corregir el mensaje y/o añadir o modificar archivos del último commit. Si quieres modificar el contenido del commit primero debes hacer los cambios, añadirlos al Staging Index y luego ejecutar el "git commit --amend". Este comando abre el editor para que adicionalmente puedas modificar el mensaje multilínea. MUY IMPORTANTE: Ejecutar este comando elimina por completo el último commit de la historia y lo reemplaza por éste. Por este motivo NO SE DEBE USAR EN REPOSITORIOS PÚBLICOS COMPARTIDOS, porque puede generar conflictos de fusión muy difíciles de solucionar.
git commit --amend -m "<nuevo-mensaje>"  // Mismas opciones que el anterior pero no abre el editor porque solo te permite escribir una línea.
git commit --amend --no-edit             // Mismas opciones que el anterior pero sin modificar el mensaje.
git commit -v                            // Abre el editor para que escribas el mensaje multilínea (si quieres) y además te muestra todos los cambios que estás apunto de comitear, así te puedes asegurar de qué estás comiteando. Es decir, es como si antes hubieras consultado los cambios con "git diff --staged", pero de este modo lo haces todo a la vez. Cuando haces el commit, Git elimina todos esos comentarios que muestra siempre de serie y los cambios que se han realizado. No sirve de nada si haces el commit con la opción "-m" porque entonces no abre el editor y no ves la lista de cambios.
```

**IMPORTANTE:** al hacer commit solo estás subiendo los cambios que están en el Staging Index en el estado en que fueron añadidos con `git add`. Si después de añadirlos has hecho más cambios, no se incluirán en el commit. Para ello es necesario actualizar primero el Staging Index con `git add -u`.

- Otra alternativa es hacer un `git commit -a`, pero este comando **no solo actualiza los archivos que ya están en el Staging Index antes de proceder al commit**. Es decir, **`git commit -a` añade al Staging Index todos (y solo) los archivos que ya están en seguimiento (y/o actualiza los que ya estuvieran en el Staging Index para incorporar todos sus cambios) antes de hacer el commit.** **IMPORTANTE:** asegúrate si esto es lo que quieres, porque como esta opción incluye todos los archivos del Working Directory que están en seguimiento, puede que en ocasiones acabes añadiendo más archivos de los que quieres.

**Al hacer commit solo se te actualiza el árbol Staging Index y el HEAD (LOCAL REPOSITORY). El Working Directory permanece en su estado actual.** Es fácil acordarse de esto recordando que puedes registrar tus cambios locales en pequeños commits (práctica recomendada) en lugar de subirlos todos de golpe. Si al hacer un commit Git hiciera que el árbol del Working Directory coincidiera con el HEAD entonces esto no sería posible.

Con `git commit --amend` puedes modificar el último commit. Pero si necesitas modificar uno o varios commits antiguos puedes usar [`git rebase`](#merge-vs-rebase).


# Historia del repositorio <a name="historia-del-repositorio"></a>


## Log <a name="log"></a>

```php
git log                                       // Ver todos los commits con toda la información. Es muy verboso.
git log --oneline                             // Ver todos los commits, pero solo su código SHA-1 y su mensaje.

git log --since="<date> [<hour>]"             // Ver todos los commits desde una fecha y hora determinada.
git log --since="19/05/2019"
git log --since="19/05/2019 17:33"

git log -<num>                                // Ver solamente los últimos "<num>" commits. Ejemplo: "git log -4".

git log --author=<name>                       // Ver todos los commits de un autor en concreto.

git log <branch-name>                         // Ver todos los commits de la rama indicada

git log --name-status                         // Ver solamente qué archivos han sido modificados en cada commit

git log -p                                    // Muestra todos los cambios de cada commit
git log --stat --summary                      // Muestra todos los cambios de cada commit. Versión resumida (solo ves el nombre del archivo y la cantidad de líneas añadidas y/o eliminadas).
git log --stat --summary --oneline            // Igual que el anterior, pero simplificado al máximo.

git log --pretty=format:"%h - %an, %ar : %s"  // Versión personalizada que muestra el Hash + AuthorName + Author date, relative + Subject. Ejemplo: ca82a6d - Scott Chacon, 6 years ago : changed the version number
```

[Opciones de personalización del `log --pretty_format`](https://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History#pretty_format)


## Reflog <a name="reflog"></a>

```php
git reflog                  // Ver historial completo del proyecto. Registro de referencia del repositorio local.
git reflog --relative-date  // Ver historial completo del proyecto con fechas relativas, del tipo "hace dos semanas".
```

- Es el `log` con el historial completo (Reflog = Reference Logs).

- Permite recuperar el estado de un proyecto anterior a pesar de haber suprimido commits realizando un `git reset --hard <ref>`, porque Git realmente no elimina del todo las referencias afectadas por un `git reset` con la opción `--hard`. Pero **MUY IMPORTANTE: las entradas del registro tienen una fecha de vencimiento**. El periodo de tiempo por defecto antes del vencimiento de una entrada es de **90 días**.

-----
**LA RED DE SEGURIDAD: GIT REFLOG**

(Fuente: https://es.atlassian.com/git/tutorials/rewriting-history)

Los registros de referencia ("reflogs") son un mecanismo que Git utiliza para registrar las actualizaciones aplicadas a los extremos de las ramas y otras referencias de commits. El comando `git reflog` te permite ir a un commit aunque no se haga referencia a este en ninguna rama o etiqueta. Después de reescribir el historial, el registro de referencia contiene información sobre el antiguo estado de las ramas y te permite volver a ese estado, si es necesario. Cada vez que la punta de tu rama se actualiza por cualquier motivo (intercambio de ramas, adición de cambios, reescritura del historial o adición de nuevos commits), se añade una nueva entrada al registro.

*[...]*

Si resulta que has tirado para atrás sin querer, el registro de referencia contendrá el commit master apuntando a `0254ea7`, antes de que perdieras accidentalmente dos commits.

```php
git reset --hard 0254ea7
```

Con el comando `git reset`, ahora es posible cambiar el master al commit que era antes. Esto proporciona una red de seguridad en caso de que se haya modificado el historial por error.

Es importante tener en cuenta que **el registro de referencia solo proporciona esta "red de seguridad" si los cambios se han confirmado en tu repositorio local y que solo realiza el seguimiento de los movimientos del extremo de la rama del repositorio.** Además, las entradas del registro tienen una fecha de vencimiento. **El periodo de tiempo por defecto antes del vencimiento de una entrada es de 90 días.**

-----

Más información en: https://es.atlassian.com/git/tutorials/rewriting-history/git-reflog


# Cambios <a name="cambios"></a>


## Significado de la cabecera de los resultados de los cambios <a name="significado-de-la-cabecera-de-los-resultados-de-los-cambios"></a>

Ejemplo:
```php
$ git diff
diff --git a/diff_test.txt b/diff_test.txt
index 6b0c6cf..b37e70a 100644
--- a/diff_test.txt
+++ b/diff_test.txt
@@ -1 +1 @@
-this is a git diff test example
+this is a diff example
```


```php
index 6b0c6cf..b37e70a 100644
```
Internal Git metadata.
These are Git object version hash identifiers.
You will most likely not need this information.


```php
--- a/diff_test.txt
+++ b/diff_test.txt
```
Legend to identify changes of each input source
In this case, changes from `a/diff_test.txt` are marked with a `---` and the changes from `b/diff_test.txt` are marked with the `+++` symbol.


```php
@@ -1 +1 @@
```
Line one had changes.

```php
@@ -34,6 +34,8 @@
```
In this more realistic header example, 6 lines have been extracted starting from line number 34. Additionally, 8 lines have been added starting at line number 34.

(Fuente: https://es.atlassian.com/git/tutorials/saving-changes/git-diff)


## Cómo resaltar mejor los cambios <a name="como-resaltar-mejor-los-cambios"></a>

```php
git diff --color-words  // ¿No funciona?
```


## Ver quién ha modificado un archivo <a name="ver-quien-ha-modificado-un-archivo"></a>

```php
git blame <file-name>  // Ver quién ha modificado un archivo, qué ha hecho, cuándo y en qué commit está cada cambio. Orden ascendente (de más antiguos a más recientes).
```


# Cómo ver cuántos archivos se han modificado del Working Directory y/o del Staging Index <a name="como-ver-cuantos-archivos-se-han-modificado-del-working-directory-y-o-del-staging-index"></a>

```php
git diff --stat          // Muestra los archivos que han sido modificados del Working Directory; y el total de archivos, inserciones y eliminaciones.
git diff --cached --stat // Muestra los archivos que han sido modificados y que están en el Staging Index; y el total de archivos, inserciones y eliminaciones.
```


# Cómo ver el total de archivos que se van a añadir al siguiente commit <a name="como-ver-el-total-de-archivos-que-se-van-a-anadir-al-siguiente-commit"></a>

```php
git diff --cached --stat // Muestra los archivos que han sido modificados y que están en el Staging Index; y el total de archivos, inserciones y eliminaciones.
```


# Cómo ver los nuevos cambios o el contenido de una referencia y/o archivo desde la consola (`show`) <a name="como-ver-los-nuevos-cambios-o-el-contenido-de-una-referencia-y-o-archivo-desde-la-consola-show"></a>

```php
git show <ref>         // Muestra los cambios de la referencia indicada con más información todavía (Commit SHA-1, Author, Date, Commit message).
git show v1.0.0        //
git show <ref> <file>  // Muestra los cambios del archivo de la referencia indicada con más información todavía (Commit SHA-1, Author, Date, Commit message). Si el archivo no ha incorporado nuevos cambios en la referencia indicada, entonces no muestra nada. Ejemplo: si en el HEAD el archivo "x" no ha incorporado nuevos cambios respecto al penúltimo commit, no mostrará nada. Pero no significa que el archivo "x" no exista en el HEAD; simplemente que no ha aportado nuevos cambios. Considerando que en el penúltimo commit sí hubiera aportado nuevos cambios, si lo ejecutas con la referencia "HEAD~" entonces sí que mostrará esos cambios.
git show <ref>:<file>  // Muestra solamente el estado (contenido) del archivo en la referencia indicada.
```


# Cómo ver la evolución de los cambios de una referencia y/o archivo (`log -p`) <a name="como-ver-la-evolucion-de-los-cambios-de-una-referencia-y-o-archivo"></a>

```php
git log -p <ref>         // Muestra los cambios de cada commit de la rama a la que pertenece la referencia indicada, desde el inicio de la rama hasta la referencia indicada.
git log -p <ref> <file>  // Muestra los cambios de cada commit de la rama a la que pertenece la referencia indicada, desde el inicio de la rama hasta la referencia indicada, pero solo relacionados con el archivo indicado.
```


## Comparar los cambios de un archivo entre dos ramas <a name="comparar-los-cambios-de-un-archivo-entre-dos-ramas"></a>

```php
git diff <rama-A> <rama-B> ./path/to/file  // Muestra los cambios específicos al contexto del archivo indicado entre las puntas de las dos ramas. Es decir, qué líneas de más y/o de menos tiene el archivo en <rama-B> comparado con <rama-A>.

//  Ejemplo:
git diff master new_branch ./diff_test.txt
```


## Cambios entre árboles (Working Directory / Staging Index / HEAD del Repositorio Local) <a name="cambios-entre-arboles-working-directory-/-staging-index-/-head-del-repositorio-local"></a>

Fuente: https://www.shellhacks.com/git-diff-staged-unstaged-files/


### Working Directory --- VS --- Staging Index <a name="working-directory-vs-staging-area"></a>

```php
git diff                 // Muestra qué cambios están pendientes de subir al Staging Index.
git diff ./path/to/file  // Muestra los nuevos cambios que tiene en el Working Directory el archivo indicado comparado con el Staging Index. Cuando se prepara el archivo para el siguiente commit, no muestra nada. Pero si antes de haber hecho un commit de los cambios anteriores se añaden aún más cambios y no se suben al Staging Index (el archivo estará en estado "MM"), este comando muestra como nuevos cambios (en verde) solo los que hay en el Working Directory (los del Staging Index aparecen en blanco). Es decir, solo muestra qué cambios están pendientes de subir al Staging Index.
```

Estos cambios solo se añadirán en el siguiente commit si se actualiza el Staging Index con "git add -u" o si se añade el flag "-a" al commit.

**IMPORTANTE**: por defecto `git diff` no muestra todos los cambios realizados desde tu último commit; **`git diff` solo muestra los cambios que todavía no has añadido al Stage**. Es decir, que si ya los has añadido todos al Staging Index y ejecutas este comando, `git diff` no te mostrará ningún resultado. Pero si antes de hacer un commit de los cambios anteriores añades aún más cambios y no los subes al Staging Index (el archivo estará en estado `MM`), este comando mostrará como nuevos cambios (en verde) solo los que hay en el Working Directory (los del Staging Index aparecerán en blanco).


### Working Directory --- VS --- HEAD <a name="working-directory-vs-head"></a>

*El HEAD normalmente será el último commit.*

```php
git diff HEAD                  // Muestra todos los nuevos cambios que hay en el Working Directory comparado con el HEAD, estén o no subidos al Staging Index (si solamente una parte de los cambios están en el Staging Index, los archivos estarán en estado "MM").
git diff HEAD ./path/to/file   // Igual que el anterior pero para el archivo indicado.
// - or -
git status -vv                 // Igual que "git diff HEAD", pero con la información verbosa de "git status".
git status -vv ./path/to/file  // Igual que el anterior pero para el archivo indicado.
```

Muestran todos los nuevos cambios que hay en el Working Directory comparado con el HEAD, estén o no subidos al Staging Index.


### Staging Index --- VS --- HEAD <a name="staging-area-vs-head"></a>

*El HEAD normalmente será el último commit.*

```php
git diff --staged  // Muestra los cambios que se añadirán en el siguiente commit si no actualizas el Staging Index con "git add -u" o si no añades el flag "-a" al commit. Compara los cambios del Staging Index con el último commit. Si hay cambios en el Working Directory pero no se han subido al Staging Index, no muestra nada.
// - or -
git diff --cached  // Muestra los cambios que se añadirán en el siguiente commit si no actualizas el Staging Index con "git add -u" o si no añades el flag "-a" al commit. Compara los cambios del Staging Index con el último commit. Si hay cambios en el Working Directory pero no se han subido al Staging Index, no muestra nada.
// - or -
git status -v      // Muestra los cambios que se añadirán en el siguiente commit si no actualizas el Staging Index con "git add -u" o si no añades el flag "-a" al commit. Compara los cambios del Staging Index con el último commit. Si hay cambios en el Working Directory pero no se han subido al Staging Index, te avisa.
```

Muestran los cambios que se añadirán en el siguiente commit si no actualizas el Staging Index con `git add -u` o si no añades el flag `-a` al commit. Compara los cambios del Staging Index con el último commit.

**TIP:** Si el día anterior tenías archivos en el Staging Index y hoy ejecutas `git diff`, no verás los cambios que ya habías subido. **Solución**: ejecutar `git diff --staged`.


## Cambios entre commits <a name="cambios-entre-commits"></a>

```php
git log -p                          // Muestra todos los cambios de cada commit
git log --stat --summary            // Muestra todos los cambios de cada commit. Versión resumida (solo ves el nombre del archivo y la cantidad de líneas añadidas y/o eliminadas).
git log --stat --summary --oneline  // Igual que el anterior, pero simplificado al máximo.

git diff <commit-A> <commit-B>      // Muestra los cambios entre las dos referencias indicadas. Es decir, qué líneas de más y/o de menos hay en el <commit-B> comparado con el <commit-A>.
```


## Cambios entre referencias (commits, ramas, etc...) <a name="cambios-entre-referencias-commits-ramas-etc"></a>

```php
git diff <ref-A> <ref-B>    // Muestra los cambios entre las dos referencias indicadas. Es decir, qué líneas de más y/o de menos hay en la <ref-B> comparada con la <ref-A>.
git diff <ref-A>..<ref-B>   // Muestra los cambios entre las dos referencias indicadas. Es decir, qué líneas de más y/o de menos hay en la <ref-B> comparada con la <ref-A>.
git diff <ref-A>...<ref-B>  // Diferencias de <ref-B> respecto al commit que comparte con <ref-A>. Es decir, ya sean <ref-A> y/o <ref-B> commits concretos (SHA-1) de ramas distintas y/o nombres de ramas distintas, <ref-A> pasa a ser el commit que comparte con <ref-B> (el commit de <ref-A> donde se creó el fork), y muestra todos los cambios que ha incorporado <ref-B> a partir del fork. Conclusión: este comando permite ver cómo ha evolucionado la rama de <ref-B> desde el fork sin tener en cuenta la evolución de la rama de <ref-A> desde el commit que comparten.

// Ejemplos
git diff HEAD^..HEAD
git diff HEAD^...HEAD
git diff <ref-A> master
git diff master origin/master
```


## Cambios de una rama desde que se hizo su fork <a name="cambios-de-una-rama-desde-que-se-hizo-su-fork"></a>

```php
git diff <ref-A>...<ref-B>  // Diferencias de <ref-B> respecto al commit que comparte con <ref-A>. Es decir, ya sean <ref-A> y/o <ref-B> commits concretos (SHA-1) de ramas distintas y/o nombres de ramas distintas, <ref-A> pasa a ser el commit que comparte con <ref-B> (el commit de <ref-A> donde se creó el fork), y muestra todos los cambios que ha incorporado <ref-B> a partir del fork. Conclusión: este comando permite ver cómo ha evolucionado la rama de <ref-B> desde el fork sin tener en cuenta la evolución de la rama de <ref-A> desde el commit que comparten.
```


## RESUMEN de comandos `git diff` <a name="resumen-de-comandos-git-diff"></a>

```php
git diff                          // Diferencias entre el Working Directory y el Staging Index
git diff ./path/to/file           // Diferencias entre el Working Directory y el Staging Index del archivo indicado.
git diff HEAD                     // Diferencias entre el Working Directory y el HEAD
git diff HEAD ./path/to/file      // Diferencias entre el Working Directory y el HEAD del archivo indicado.
git diff --staged                 // Diferencias entre el Staging Index (¡OJO! Actualizarlo primero) y el HEAD
git diff --staged ./path/to/file  // Diferencias entre el Staging Index (¡OJO! Actualizarlo primero) y el HEAD del archivo indicado.
git diff --cached                 // Diferencias entre el Staging Index (¡OJO! Actualizarlo primero) y el HEAD
git diff --cached ./path/to/file  // Diferencias entre el Staging Index (¡OJO! Actualizarlo primero) y el HEAD del archivo indicado.
git diff <ref-A> <ref-B>          // Diferencias de <ref-B> respecto a <ref-A>
git diff <ref-A> <ref-B> [--stat] [--] ./path/to/file  // Diferencias de <ref-B> respecto a <ref-A> del archivo indicado.
git diff <ref-A> <ref-B> [--stat] [--] .<dir>          // Diferencias de <ref-B> respecto a <ref-A> del directorio indicado.
git diff <ref-A>..<ref-B>                              // Diferencias de <ref-B> respecto a <ref-A> (es exactamente igual que usar un espacio entre las dos referencias).
git diff <ref-A>...<ref-B>                             // Diferencias de <ref-B> respecto al commit que comparte con <ref-A>. Es decir, ya sean <ref-A> y/o <ref-B> commits concretos (SHA-1) de ramas distintas y/o nombres de ramas distintas, <ref-A> pasa a ser el commit que comparte con <ref-B> (el commit de <ref-A> donde se creó el fork), y muestra todos los cambios que ha incorporado <ref-B> a partir del fork. Conclusión: este comando permite ver cómo ha evolucionado la rama de <ref-B> desde el fork sin tener en cuenta la evolución de la rama de <ref-A> desde el commit que comparten.
```


## Revisar cambios de un/a compañero/a obtenidos de un repositorio remoto antes de hacer merge en tu rama <a name="revisar-cambios-de-un-a-companero-a-obtenidos-de-un-repositorio-remoto-antes-de-hacer-merge-en-tu-rama"></a>

```php
// Alice quiere revisar los cambios de Bob
git fetch /home/bob/myrepo master
git log -p HEAD..FETCH_HEAD  // Ver todo lo que tiene Bob y Alice no
```

Hacer esto es SEGURO incluso si Alice todavía tiene cambios locales sin comitear.

También puedes **ver vuestras diferencias** con estos comandos:

```php
gitk HEAD..FETCH_HEAD      // Ver todo lo que tiene Bob y Alice no
// - or -
git log HEAD..FETCH_HEAD   // Ver todo lo que tiene Bob y Alice no

gitk HEAD...FETCH_HEAD     // Ver todo lo que cada uno ha hecho desde que hicísteis el FORK (los commits compartidos no se tienen en cuenta).
// - or -
git log HEAD...FETCH_HEAD  // Ver todo lo que cada uno ha hecho desde que hicísteis el FORK (los commits compartidos no se tienen en cuenta).
```

**Si después de revisar los cambios crees que:**

 - **NO debes incorporarlos:** simplemente sigue trabajando como estabas y ya está. Ésta es la ventaja de usar `git fetch` en lugar de hacer un `git pull` directamente, en cuyo caso hubiera forzado el merge.

 - **SÍ debes incorporarlos:** sigue estos pasos:

   1. `git stash save [-k|-u|-a] "<mensaje>"` para salvar el trabajo en tu estado actual.

   2. `git pull`

   3. `git stash apply`, así recuperarás tu trabajo por encima de la historia actual. Con lo cual almenos estarás seguro de que lo haces en la versión actual del repositorio. Aún así podría ser que aquí tuvieras que resolver algún conflicto provocado por tus cambios locales.


# Checkout <a name="checkout"></a>

**IMPORTANTE:** el comando `git checkout` tiene comportamientos totalmente distintos según si opera con commits o con archivos.

En los siguientes enlaces a las tablas de resumen puedes verlo de manera simplificada:

- [TABLA RESUMEN: Alcance de RESET y CHECKOUT](#tabla-resumen-alcance-de-reset-y-checkout)

- [TABLA RESUMEN: Usos comunes y alcance de RESET, CHECKOUT y REVERT](#tabla-resumen-usos-comunes-y-alcance-de-reset-checkout-y-revert)


```php
// RESUMEN CON COMENTARIOS SIMPLIFICADOS
git checkout -- .                    // /!\ SE PIERDEN CAMBIOS LOCALES. Actualiza: Working Directory                        por todos los archivos del Staging Index (solo los que tengan en común).
git checkout -- <file-name>          // /!\ SE PIERDEN CAMBIOS LOCALES. Actualiza: Working Directory                        por el archivo en común que actualmente está en el Staging Index.
git checkout HEAD -- .               // /!\ SE PIERDEN CAMBIOS LOCALES. Actualiza: Working Directory + Staging Index        por todos los archivos del HEAD (solo los que tengan en común).
git checkout HEAD -- <file-name>     // /!\ SE PIERDEN CAMBIOS LOCALES. Actualiza: Working Directory + Staging Index        por el archivo en común del HEAD.
git checkout <ref> -- <file-name>    // /!\ SE PIERDEN CAMBIOS LOCALES. Actualiza: Working Directory + Staging Index        por el archivo en común de la referencia indicada.
git checkout <ref>                   //  NO SE PIERDEN CAMBIOS LOCALES. Actualiza: Working Directory + Staging Index + HEAD por todos los archivos de la referencia indicada. ES SEGURO: si detecta que vas a perder cambios locales aborta la operación y te sugiere guardar los cambios.
```

**Más información importante en este apartado:** [Deshacer cambios de un archivo con CHECKOUT [PELIGROSO]](#deshacer-cambios-de-un-archivo-con-checkout-peligroso).

```php
git checkout -- .                                           // Reemplaza los archivos del Working Directory por todos los archivos del Staging Index (solo los que tengan en común).
git checkout HEAD -- .                                      // Reemplaza los archivos del Working Directory y del Staging Index por todos los archivos del HEAD (solo los que tengan en común).
git checkout -- <file-name>                                 // Reemplaza el archivo del Working Directory por el archivo en común que actualmente está en el Staging Index. Si acabas de hacer un commit coincidirá con el del HEAD. Pero si has hecho cambios y los has subido al Staging Index, su código SHA-1 habrá cambiado y ya no coincidirá con el del HEAD. Si después de subir al Staging Index estos primeros cambios (sin llegar a hacer commit) continuas haciendo más cambios, al ejecutar este comando, en el Working Directory el archivo se quedará en el mismo estado del que está en el Staging Index, es decir, con esos primeros cambios que ya habías subido; y al hacer un "git status" te aparecerá con el estado "M ". El archivo del Staging Index tampoco coincidirá con el del HEAD cuando hayas ejecutado un `git reset --mixed <ref> -- <file>`, porque este comando solo te copia en tu Staging Index el estado del archivo de la referencia indicada (en este caso ésta será la versión que usará para reemplazar tu archivo del Working Directory) sin afectar ni al HEAD ni al Working Directory.
git checkout HEAD -- <file-name>                            // Reemplaza el archivo del Working Directory y del Staging Index por el archivo en común del HEAD.
git checkout <ref> -- <file-name>                           // Reemplaza el archivo del Working Directory y del Staging Index por el archivo en común de la referencia indicada.

git checkout <ref> -- file1/to/restore file2/to/restore     // Lo mismo que el anterior pero con varios archivos.
git checkout c5f567 -- file1/to/restore file2/to/restore    //
git checkout c5f567~1 -- file1/to/restore file2/to/restore  //
```

```php
git checkout                                    // NO HACE NADA
git checkout <ref>                              // Mueve el HEAD a la referencia indicada. Si <ref> no es el nombre de una rama, entras en modo "detached HEAD". Es decir, cualquier código SHA-1 de un commit, aunque sea el que corresponda con el último de una rama, te deja en modo "detached HEAD".
git checkout -b <branch-name>                   // Crea una nueva rama a partir del commit donde estás y mueve el HEAD a ella directamente. Si acabas de entrar en el modo "detached HEAD", te soluciona este problema.
git checkout -b <new-branch> <existing-branch>  // Crea una nueva rama a partir del commit que le indiques (aunque no estés ahí) y mueve el HEAD a ella directamente. Al indicar el commit de referencia, este comando también lo puedes ejecutar estando en otra rama. Te evita entrar en modo "detached HEAD" cuando te mueves atrás en la historia.
git checkout -b <branch-name> <sha1>            // Recupera una rama eliminada a partir de su nombre y SHA-1. Si no sabes el SHA-1 de la punta de la rama lo puedes consultar con "git reflog".
```

> `--` significa que todos los argumentos que le pasemos a continuación los considere nombres de archivos.


## AVISO: Detached HEAD <a name="aviso-detached-head"></a>

Este tema está relacionado con el comando `git checkout` y `git rebase`.


### Cuándo y por qué aparece este aviso <a name="cuando-y-por-que-aparece-este-aviso"></a>

Lo más habitual es que nos desplacemos entre ramas por su nombre, en cuyo caso Git nos ubica en el extremo final de la rama y en nuestro Working Directory se muestran los archivos correspondientes a ese estado del proyecto. En esta situación, si hacemos un commit los cambios se guardan en esa rama y Git desplaza automáticamente el puntero HEAD para que esté justo después de este último commit.

En cambio, cuando nos desplazamos en el tiempo tomando una referencia *hash* de commit (SHA-1) en lugar de un nombre de rama, en nuestro Working Directory también se muestran los archivos correspondientes a ese estado del proyecto (para que podamos revisar cómo estaban los archivos en ese instante), pero Git entra en modo `Detached HEAD`, que significa que:

  - Git considera que no estamos en ninguna rama.

  - Si hacemos un commit en ese punto, no pertenecerá a ninguna rama.

  - Al no estar registrados los cambios en el contexto de nunguna rama, quedarán huérfanos y no será posible acceder a ellos si posteriormente nos desplazamos a otra rama haciendo otro `checkout`.

**Es perfectamente válido desplazarse a un commit SHA-1 en concreto para revisar cómo funcionaba una versión anterior y/o para probar nuevos cambios alternativos a partir de ese punto. Simplemente hay que hacerlo de la mejor manera posible, la que se indica abajo en la solución.**

> **Si solamente queremos ver el estado de los archivos de los commits anteriores sin pretender añadir nuevos cambios**, podemos hacerlo de diferentes maneras:
> 
> - **Opción 1 (involución de los cambios):**
>   
>   **Moverte hacia atrás de commit en commit**, por ejemplo, con `git checkout HEAD~` (o `git checkout <commit>~` si quieres partir desde un punto concreto distinto a HEAD). De este modo puedes ir viendo fácilmente la **in**volución de un archivo desde el editor ATOM, por ejemplo, porque se sincroniza con el repositorio.
>   
>   Recuerda: como `git checkout` mueve el HEAD, cada vez que te desplazas de commit el HEAD pasa a estar en el commit en el que te encuentras. Esto debes tenerlo en cuenta al usar el indicador `~<num>`, porque se moverá las posiciones que le indiques tomando como referencia el nuevo HEAD. Por eso, si ejecutas una y otra vez `git checkout HEAD~` siempre te mueves una posición más hacia atrás.
>   
>   Cuando terminas de ver versiones anteriores, ejecutas `git checkout master` y Git te devuelve al final de la rama master saliendo del modo `detached HEAD`.
> 
> - **Opción 2 (cambios y/o estado concreto):**
> 
>   **Ver en la consola (no en el editor) los nuevos cambios que ha aportado una referencia y/o archivo en concreto** con `git show <ref> <file>` (si la referencia y/o archivo indicado no ha aportado nuevos cambios no muestra nada); **o ver solamente el estado (contenido) del archivo en la referencia indicada** con `git show <ref>:<file>`. Así te aseguras de que no entras en modo `detached HEAD` ni que puedas perder accidentalmente ningún cambio local.
>   
> - **Opción 3 (evolución de los cambios):**
>   
>   **Ver en la consola (no en el editor) los cambios de cada commit de la rama a la que pertenece la referencia indicada, desde el inicio de la rama hasta la referencia indicada** con `git log -p <ref>`; **o ver solamente los cambios relacionados con el archivo indicado** con `git log -p <ref> <file>`.

Este aviso también aparece cuando hacemos un `git rebase`, porque este comando crea un `detached HEAD temporal`. En este caso basta con hacer un `git checkout master` para salir de ese estado.

(Fuente: https://www.git-tower.com/learn/git/faq/detached-head-when-checkout-commit)


### SOLUCIÓN <a name="detached-head-solucion"></a>

- Si acabamos de entrar en modo detached HEAD:
  
  ```php
  git checkout -b <nombre-rama-para-tests>  // Crear una rama desde el commit hash concreto donde te encuentras y desplazarte a ella automáticamente
  ```
  
- Si queremos evitar el aviso:
  
  ```php
  git checkout -b <nombre-rama-para-tests> <commit-hash>  // Crear una rama desde un commit hash concreto y desplazarte a ella automáticamente
  
  
Y cuando ya no queramos los cambios que hemos creado en la nueva rama:

```php
git checkout master                     // Volver al último commit de la rama master
git branch -d <nombre-rama-para-tests>  // Eliminar la rama de tests
```

De este modo creamos una rama en la cual vamos a poder registrar los cambios sin problemas para poder acceder a ellos nuevamente cuando queramos y/o eliminarlos cuando hayamos acabado de hacer las pruebas.


# Deshacer cambios <a name="deshacer-cambios"></a>


## Deshacer cambios de un archivo con CHECKOUT [PELIGROSO] <a name="deshacer-cambios-de-un-archivo-con-checkout-peligroso"></a>

- **IMPORTANTE: se pierden todos los cambios locales y no es posible recuperarlos. no usarlo si no estás 100% seguro si se pueden eliminar.** En este caso es mejor que crees una nueva rama o que guardes primero los cambios en un nuevo [stash](#como-guardar-tu-trabajo-cuando-esta-a-medias-y-no-quieres-perderlo-stash).

- **IMPORTANTE:** depende de la referencia que le pases a `git checkout`, modifica el archivo en seguimiento del Working Directory por el estado del archivo en común del Staging Index o del HEAD. Es decir, **no es lo mismo `git checkout -- <file-name>` que `git checkout HEAD -- <file-name>`** (`HEAD` puede ser cualquier otra referencia):

  - **`git checkout -- <file-name>`**
    
    Reemplaza el archivo del Working Directory por el archivo en común que actualmente está en el Staging Index.
    
    Si acabas de hacer un commit coincidirá con el del HEAD. Pero si has hecho cambios y los has subido al Staging Index, su código SHA-1 habrá cambiado y ya no coincidirá con el del HEAD. Si después de subir al Staging Index estos primeros cambios (sin llegar a hacer commit) continuas haciendo más cambios, al ejecutar este comando, en el Working Directory el archivo se quedará en el mismo estado del que está en el Staging Index, es decir, con esos primeros cambios que ya habías subido; y al hacer un `git status` te aparecerá con el estado `M `.
    
    El archivo del Staging Index tampoco coincidirá con el del HEAD cuando hayas ejecutado un `git reset --mixed <ref> -- <file>`, porque este comando solo te copia en tu Staging Index el estado del archivo de la referencia indicada (en este caso ésta será la versión que usará para reemplazar tu archivo del Working Directory) sin afectar ni al HEAD ni al Working Directory.

  - **`git checkout HEAD -- <file-name>`**
    
    Reemplaza el archivo del Working Directory y del Staging Index por el archivo en común del HEAD.

  - **`git checkout <ref> -- <file-name>`**
    
    Reemplaza el archivo del Working Directory y del Staging Index por el archivo en común de la referencia indicada.

> Como podemos ver, aunque normalmente cuando no se indica una referencia por defecto Git toma el HEAD como *target* (`<ref>`), en este caso no se comporta como esperaríamos.

```php
git checkout -- .                                           // Reemplaza los archivos del Working Directory por todos los archivos del Staging Index (solo los que tengan en común).
git checkout HEAD -- .                                      // Reemplaza los archivos del Working Directory y del Staging Index por todos los archivos del HEAD (solo los que tengan en común).
git checkout -- <file-name>                                 // Reemplaza el archivo del Working Directory por el archivo en común que actualmente está en el Staging Index. Si acabas de hacer un commit coincidirá con el del HEAD. Pero si has hecho cambios y los has subido al Staging Index, su código SHA-1 habrá cambiado y ya no coincidirá con el del HEAD. Si después de subir al Staging Index estos primeros cambios (sin llegar a hacer commit) continuas haciendo más cambios, al ejecutar este comando, en el Working Directory el archivo se quedará en el mismo estado del que está en el Staging Index, es decir, con esos primeros cambios que ya habías subido; y al hacer un "git status" te aparecerá con el estado "M ". El archivo del Staging Index tampoco coincidirá con el del HEAD cuando hayas ejecutado un `git reset --mixed <ref> -- <file>`, porque este comando solo te copia en tu Staging Index el estado del archivo de la referencia indicada (en este caso ésta será la versión que usará para reemplazar tu archivo del Working Directory) sin afectar ni al HEAD ni al Working Directory.
git checkout HEAD -- <file-name>                            // Reemplaza el archivo del Working Directory y del Staging Index por el archivo en común del HEAD.
git checkout <ref> -- <file-name>                           // Reemplaza el archivo del Working Directory y del Staging Index por el archivo en común de la referencia indicada.

git checkout <ref> -- file1/to/restore file2/to/restore     // Lo mismo que el anterior pero con varios archivos.
git checkout c5f567 -- file1/to/restore file2/to/restore    //
git checkout c5f567~1 -- file1/to/restore file2/to/restore  //
```

> `--` significa que todos los argumentos que le pasemos a continuación los considere nombres de archivos.


## Deshacer cambios de un archivo con RESET [N/D] <a name="deshacer-cambios-de-un-archivo-con-reset-no-se-puede"></a>

Usando `git reset` no es posible devolver un archivo del Working Directory a un estado concreto, ni tomando la versión del HEAD ni la de otra referencia. La única manera de lograrlo es con [`git checkout`](#deshacer-cambios-de-un-archivo-con-checkout-peligroso).

A nivel de archivos `git reset` solo permite reemplazar la versión que está en el Staging Index:

```php
// Reset con ruta de archivo
git reset --soft [<ref>] <file>   // NO EXISTE: fatal: Cannot do soft reset with paths.
git reset --mixed [<ref>] <file>  // SÍ EXISTE: copia el archivo en su estado de la referencia indicada (o HEAD por defecto) al Staging Index, pero no modifica el Working Directory. ES SEGURO.
git reset --hard [<ref>] <file>   // NO EXISTE: fatal: Cannot do hard reset with paths.

// Las opciones "--soft" y "--hard" no existen a nivel de archivo, porque cuando se usa `git reset` con archivos SIEMPRE actualiza el Staging Index, y NUNCA actualiza ni el HEAD ni el Working Directory.
```


## Deshacer commits con RESET [PELIGROSO] <a name="deshacer-commits-con-reset-peligroso"></a>

> Se recomienda [deshacer commits con `git revert`](#deshacer-commits-con-revert-recomendado).

- **MUY IMPORTANTE:** SOLO USAR `git reset <commit>` EN REPOSITORIOS LOCALES PERSONALES. NUNCA EN REPOSITORIOS PÚBLICOS O DEL TRABAJO. EVITAR USARLO SI SE HAN CREADO NUEVOS COMMITS POSTERIORES A `<commit>` QUE YA HAN SIDO SUBIDOS A UN REPOSITORIO PÚBLICO.

- Por defecto `git reset` usa como *target* el HEAD (no el HEAD~) y la opción `--mixed`. Por eso `git reset HEAD` es idéntico a hacer `git reset --mixed HEAD`.

- El comando `git reset <commit>` sobreescribe los tres árboles en un orden específico. Se detiene en el que tú le digas usando la opción correspondiente (`--soft`, `--mixed` (*default*) o `--hard`):

  1. Mueve la rama a la que apunta el HEAD (se detiene aquí si se usa la opción `--soft`).

  2. Hace que el Staging Index coincida con el estado del HEAD (se detiene aquí si se usa la opción `--mixed`. Es el comportamiento por defecto de `git reset`).

  3. Hace que el Working Directory coincida con el estado del Staging Index (se detiene aquí si se usa la opción `--hard`).

  (Fuente: https://scottchacon.com/2011/07/11/reset.html)

- **Diferencia entre `git checkout <ref>` y `git reset <ref>`:**

  ![Reset VS Checkout sobre el HEAD](https://git-scm.com/book/en/v2/images/reset-checkout.png)

  - **`git checkout <ref>`:**
    - **Mueve el HEAD en sí mismo, de modo que el final de la rama sigue siendo su último commit; y reemplaza el Staging Index y el Working Directory para que coincida con el estado de `<ref>`.** Pero **en el caso de que detecte que se van a perder cambios locales, aborta la operación.**
       
    - **Es seguro a nivel de commits, pero no con rutas de archivos,** en cuyo caso reemplaza el Staging Index y el Working Directory sin preguntar y pierdes los cambios locales.
       
    - Se comporta igual tanto si la referencia pertenece a la rama actual como a otra.

    - Te deja en [modo "Detached HEAD"](#aviso-detached-head) (situación no recomendada) si le pasas como referencia un código SHA-1 de commit, aunque sea el de la punta de una rama. Solamente si le pasas el nombre de una rama evitas entrar en el modo "Detached HEAD".

  - **`git reset <ref>`:**

    - **Mueve el puntero del HEAD y hace que la rama termine en el commit que se haya indicado, dejando huérfanos los commits posteriores a `<ref>`, que acabarán siendo eliminados** por el Garbage Collector.

      > Cuando decimos que "hace que la rama termine en el commit que se haya indicado" es porque, además de mover el puntero del HEAD, también resetea el Commit History (la historia de la rama). Puedes comprobarlo ejecutando `git log` justo después de ejecutar un `git reset`: el Commit History habrá sido reseteado, porque solo contendrá los commits existentes hasta el commit al que te has desplazado. Los demás ya no estarán.
      >
      > Gráficamente se podría representar de la siguiente manera:
      > 
      > `.---*---*---*---*---*---*---*<[HEAD]`
      > 
      > `.---*---*---*<[HEAD]    *---*---*---*`

      Si en este punto creamos un nuevo commit, será el nuevo HEAD de la rama, porque el original lo acabamos de dejar huérfano.
       
    - **Una vez ejecutado el `git reset <ref>`, los commits posteriores a `<ref>` ya han quedado huérfanos,** (incluso haciendo un `git reset --soft <ref>`).
       
      Si inmediatamente después consultas el `git log`, puedes comprobar que ya ha dejado huérfanos dichos commits porque no te los muestra.
       
      Si en este punto ejecutas `git checkout <branch-name>` pretendiendo volver a la punta original de la rama actual (o moviéndote primero a otra rama y volviendo de nuevo a ésta por su nombre o por el SHA-1 de su último commit original), no lograrás recuperar los commits huérfanos.
         
      **Pero aún puedes recuperar la situación anterior, siempre y cuando el `reset` haya sido con la opcion `--mixed` (la opción por defecto) o `--soft`:** [Cómo deshacer un `git reset --soft` o `--mixed`](#como-deshacer-un-git-reset-soft-o-mixed)

- **La única manera de hacer que el comando `git reset` sea peligroso es usando la opción `--hard`**, siendo una de los pocos casos en los que Git realmente eliminará información (del Working Directory se refiere; porque lo de dejar commits huérfanos ocurre por igual con sus tres opciones disponibles).

  Como la base de datos de Git aún conserva el commit de la versión eliminada, aún es posible recuperarla consultando `git reflog` (**solo durante 90 días, por defecto**). Pero si no exisitiera un commit de esa información entonces sí que sería del todo irrecuperable.

- Si te desplazas varios commits hacia atrás con la opción `--soft` (en lugar de hacer `git reset --soft HEAD~` que te sitúa justo en el commit anterior al HEAD), al hacer un `git status` ves archivos actuales en el Staging Index con el estado `modified` que todavía no existían en el commit en el que te encuentras. Esto es debido a que solo ha modificado el HEAD para que el final del *Commit History* coincida con la referencia indicada, pero no ha modificado ni el Staging Index ni el Working Directory.
 
  Con esto `git status` te está indicando que el Staging Index está por delante de los cambios regsitrados en el nuevo HEAD del *Commit History*. Dicho de otra manera, es la diferencia entre tu verdadero Staging Index actual (el que corresponde con el último commit de antes de hacer el reset) y el commit en el que te encuentras. Es decir, estás contrastando el estado actual real del proyecto con ese estado del pasado, pudiendo crear un nuevo commit que incorpore cambios recientes de archivos que ya existían en ese commit del pasado y/o incorporar archivos nuevos al commit en el que te encuentras, que es mucho anterior a la creación de dichos ficheros.


### Efectos de cada tipo de reset <a name="efectos-de-cada-tipo-de-reset"></a>

- **`git reset --soft <ref>`**
  
  - Solo mueve el HEAD, dejando huérfanos los commits posteriores a `<ref>`, que acabarán siendo eliminados del log `git log` por el Garbage Collector.
  
  - No actualiza el contenido del Staging Index ni del Working Directory.

- **`git reset --mixed <ref>`**
  
  - Mueve el HEAD, dejando huérfanos los commits posteriores a `<ref>`, que acabarán siendo eliminados del log `git log` por el Garbage Collector.
  
  - Y actualiza el Staging Index, haciéndolo coincidir con el contenido al que apunta la referencia indicada.

- **`git reset --hard <ref>`**
  
  - Mueve el HEAD, dejando huérfanos los commits posteriores a `<ref>`, que acabarán siendo eliminados del log `git log` por el Garbage Collector.
  
  - Y actualiza el Staging Index y el Working Directory, haciéndolos coincidir con el contenido al que apunta la referencia indicada.
  
  - Los tres árboles tienen el mismo contenido. Te deja como si acabaras de hacer el commit de `<ref>`.
  
  - **IMPORTANTE: se pierden todos los cambios locales que no se hayan guardado (solo de los archivos que están en seguimiento) y no es posible recuperarlos.** Pero **no pierdes los archivos nuevos que todavía no hayas añadido al Staging Index.**
     
    - Con "guardado" se refiere a que los hayas guardado en Git con un stash, commit, o rama aparte, por ejemplo. Es necesario precisar esto porque si tienes los tres árboles en el estado del último commit y haces cambios en un archivo sin guardarlos (en el sentido de `Ctrl+S`), si luego haces un `git reset --hard HEAD` te sorprende porque sigues viendo tus cambios en lugar de reemplazarte todo su contenido por lo que realmente contiene la versión del HEAD. En cambio, si haces modificaciones y las guardas con `Ctrl+S`, al cambiar su SHA-1, si haces el `git reset --hard HEAD`, entonces sí que te reemplaza todo el contenido, porque detecta que el estado del archivo ha cambiado. Pasa exactamente lo mismo con `git checkout HEAD -- .`

      > Realmente este comportamiento es lógico, porque Git controla el estado de los índices internos de cada árbol basándose en los `SHA-1 checksum` de los archivos.
      > 
      > De modo que si tú ya estás en el último commit, por mucho que modifiques su contenido y mientras no hagas `Ctrl+S`, la referencia de tu archivo seguirá siendo la misma, porque los SHA-1 cambian cuando guardas los cambios (y/o cuando añades el archivo al Staging Index). Entonces, si en este instante haces el `git reset --hard HEAD`, no pierdes lo que has escrito y/o eliminado, porque como su código SHA-1 no ha sido modificado, coincide con el del HEAD y no necesita actualizarlo.

    - Aunque siempre se diga que al ejecutar `git reset --hard <ref>` pierdes por completo todos los cambios locales del Working Directory, esto solo afecta a los archivos del Working Directory que están en seguimiento; que son los que ya han formado parte de un commit, y los archivos nuevos que están en el Staging Index pero que nunca han sido añadidos a un commit.
    
      De modo que **no pierdes los archivos nuevos que todavía no hayas añadido al Staging Index.** Porque si bien `git reset --hard <ref>` te deja el Working Directory exactamente como se encontraba en la referencia indicada, solo reemplaza los archivos en seguimiento. Todos los demás los sigues conservando.

    - Si ejecutas `git reset --hard <nombre-otra-rama>` dejas huérfanos todos los commits que pertenecen a la rama que estás abandonando, porque ahora la referencia a la que apunta su HEAD es el último commit de la rama de destino `<nombre-otra-rama>`. En este punto podrías eliminar la rama de destino, porque ahora sus commits también forman parte de la rama que has reseteado y no se perderán.

```php
git reset --soft <ref>   // Solo mueve el HEAD (dejando huérfanos los commits posteriores a <ref>, que acabarán siendo eliminados del log `git log` por el Garbage Collector), pero no actualiza el contenido del Staging Index ni del Working Directory.
git reset --soft HEAD~   // (Nótese el uso de "~" después del HEAD) Equivale a hacer un "git commit --amend", porque solo mueve el HEAD una posición atrás, pero no actualiza el contenido del Staging Index ni del Working Directory. Es decir, te deja como si no hubieras hecho el último "git commit" solamente. Entonces puedes hacer los cambios que quieras, luego subirlos al Staging Index y, al hacer el nuevo commit, reemplazas por completo el último commit por este nuevo sin dejar rastro en la historia. [Nota: técnicamente no es idéntico a "git commit --amend", porque "reset" mueve el HEAD y "git commit --amend" lo cambia.

git reset --mixed <ref>  // Mueve el HEAD (dejando huérfanos los commits posteriores a <ref>, que acabarán siendo eliminados del log `git log` por el Garbage Collector) y actualiza el Staging Index, haciéndolo coincidir con el contenido al que apunta la referencia indicada.
git reset --mixed HEAD~  // Mueve el HEAD (dejando huérfanos los commits posteriores a <ref>, que acabarán siendo eliminados del log `git log` por el Garbage Collector) y actualiza el Staging Index, haciéndolo coincidir con el contenido al que apunta la referencia indicada (HEAD~). Te deja como si no hubieras hecho el último "git add" y "git commit" (en este ejemplo). Es decir, llega incluso a quitar los archivos del Staging Index (les hace un "unstage") y los ves en el Working Directory, porque estás como si aún no hubieras elegido qué archivos formarán parte del snapshot del siguiente commit. Es decir, el HEAD y el Staging Index corresponden con el estado de la referencia indicada, pero tu Working Directory es el actual.

git reset --hard <ref>   // Mueve el HEAD (dejando huérfanos los commits posteriores a <ref>, que acabarán siendo eliminados del log `git log` por el Garbage Collector) y actualiza el Staging Index y el Working Directory, haciéndolos coincidir con el contenido al que apunta la referencia indicada. Los tres árboles tienen el mismo contenido. Te deja como si acabaras de hacer el commit de <ref>. IMPORTANTE: SE PIERDEN TODOS LOS CAMBIOS LOCALES QUE NO SE HAYAN GUARDADO (solo de los archivos que están en seguimiento) Y NO ES POSIBLE RECUPERARLOS. Pero no pierdes los archivos nuevos que todavía no hayas añadido al Staging Index.
git reset --hard HEAD~   // Mueve el HEAD (dejando huérfanos los commits posteriores a <ref>, que acabarán siendo eliminados del log `git log` por el Garbage Collector) y actualiza el Staging Index y el Working Directory, haciéndolos coincidir con el contenido al que apunta la referencia indicada (HEAD~ en este caso). Los tres árboles tienen el mismo contenido. Te deja como si acabaras de hacer el commit anterior (en este ejemplo). IMPORTANTE: SE PIERDEN TODOS LOS CAMBIOS LOCALES QUE NO SE HAYAN GUARDADO (solo de los archivos que están en seguimiento) Y NO ES POSIBLE RECUPERARLOS. Pero no pierdes los archivos nuevos que todavía no hayas añadido al Staging Index. Elimina del log (`git log`) todos los commits posteriores a la referencia indicada.


// NOTA ADICIONAL: Reset con ruta de archivo
git reset --soft [<ref>] <file>   // NO EXISTE: fatal: Cannot do soft reset with paths.
git reset --mixed [<ref>] <file>  // SÍ EXISTE: copia el archivo en su estado de la referencia indicada (o HEAD por defecto) al Staging Index, pero no modifica el Working Directory. ES SEGURO.
git reset --hard [<ref>] <file>   // NO EXISTE: fatal: Cannot do hard reset with paths.

// Las opciones "--soft" y "--hard" no existen a nivel de archivo, porque cuando se usa `git reset` con archivos SIEMPRE actualiza el Staging Index, y NUNCA actualiza ni el HEAD ni el Working Directory.
```


### Cómo deshacer un `git reset --soft` o `--mixed` <a name="como-deshacer-un-git-reset-soft-o-mixed"></a>

**Para volver al estado anterior del reset debes conocer el `SHA-1` del último commit que había antes del reset** (el `SHA-1` del último commit lo puedes obtener del historial `git reflog`, pero **solo durante 90 días, por defecto**)y **seguir los siguientes 4 pasos**:
    
1. `git checkout -b <new-branch-name> <ref>`

    Usamos como referencia el commit de la antigua punta de la rama.

    Creamos una nueva rama a partir de la esta referencia y automáticamente nos mueve a ella.
      
    Vuelven a aparecer los commits huérfanos en el `git log`, pero siguen sin pertenecer a su rama original. Por ahora solo pertenecen a la nueva rama, pero almenos ya los hemos salvado.

2. `git checkout <branch-name>`

    Nos movemos a la rama anterior donde habíamos hecho el reset.

3. `git merge <new-branch-name>`

    Hacemos un merge de la nueva rama que hemos creado con el propósito de salvar los commits huérfanos. Resuelve el merge con un *Fast-forward*.

    **Ya hemos recuperado el estado original de la rama reseteada.**

    **Los commits recuperados siguen teniendo el mismo código SHA-1 que antes.**

4. `git branch -d <new-branch-name>`

    Eliminamos la nueva rama porque ya no la necesitamos.


## Deshacer commits con REVERT [RECOMENDADO] <a name="deshacer-commits-con-revert-recomendado"></a>

- Es el método ideal para trabajar en repositorios públicos compartidos.

- Solo funciona con commits, no con archivos.

- No elimina ningún commit de la historia.

- No elimina el commit de referencia. Gracias a esto, incluso después de hacer el *revert* es posible recuperar esa versión.

- Crea un nuevo commit (*revert commit*) al final de la rama con el resultado de eliminar al estado actual del proyecto solamente los cambios que introdujo el commit de referencia. Es decir, invierte los cambios introducidos por el commit indicado, manteniendo todos los cambios de los commits posteriores (si los hay). En el caso de que la referencia sea `HEAD`, el resultado obtenido será como si se hubiera eliminado el último commit.

- Si es posible hacer el *revert*, se abre el editor que tengas asociado a Git para que escribas un mensaje o dejes el que hay por defecto: `Revert "<mensaje-del-commit-de-referencia>"`.

- Si no es posible hacer el *revert*, te avisa con mensajes como los siguientes:
  
  ```
  error: Reverting is not possible because you have unmerged files.
  hint: Fix them up in the work tree, and then use 'git add/rm <file>'
  hint: as appropriate to mark resolution and make a commit.
  fatal: revert failed

  // - or -

  error: could not revert c368ce8... 1
  hint: after resolving the conflicts, mark the corrected paths
  hint: with 'git add <paths>' or 'git rm <paths>'
  hint: and commit the result with 'git commit'
  ```

- Si tienes cambios locales sin guardar te avisa para que los guardes en Git haciendo un `commit` o creando un `stash` y aborta el *revert* (en este aspecto se comporta igual que `git checkout` cuando la referencia que le pasas es un commit, no un archivo).

  ```
  error: your local changes would be overwritten by revert.
  hint: commit your changes or stash them to proceed.
  fatal: revert failed
  ```

- Igual que hacen `git checkout` y `git reset`, `git revert` toma un commit como referencia. Pero a diferencia de ellos, `git revert` no mueve la referencia del puntero HEAD a ese commit: solo **invierte los cambios del commit indicado**, creando un nuevo commit (*"revert commit"*) al final de la rama en el que ya no estarán esos cambios que introdujo.

- Si no se le pasa un commit de referencia muestra la ayuda de este comando, pero no hace nada.

- Es posible revertir más de un commit. Ejemplo: revertir los 3 últimos commits:
  
  ```php
  git revert HEAD~3..HEAD  // Revertir los 3 últimos commits
  ```

- **CONSEJO:** como este comando se asegura de que no pierdas ningún cambio local que no forme parte del historial de Git, una vez lo tengas guardado, y para no correr ningún riesgo, siempre puedes **usar la opción `-n | --no-commit` para que solo te añada al Staging Index y al Working Directory el resultado. Y si ves que no es lo que necesitas, puedes ejecutar `git revert --abort` para descartarlo todo** y que no te obligue a hacer el commit después del revert que te insiste en hacer para confirmar y guardar los cambios.

- El único caso en el que no será apropiado usar `git revert` es cuando exista el requisito de mantener en la historia el menor número posible de commits de calidad.

(Fuente: https://es.atlassian.com/git/tutorials/undoing-changes/git-revert)

```php
git revert                                           // Muestra la ayuda de este comando, pero no hace nada. Es necesario indicarle una referencia.
git revert <ref>                                     // Crea un nuevo commit al final de la rama para que el estado del proyecto sea el resultado de eliminar al estado actual solamente los cambios que introdujo el commit de referencia. Si en el log hay otros commits después de la referencia, sus cambios no se eliminan.
git revert <-n|--no-commit> <ref>                    // No crea un nuevo commit al final de la rama. Añade al Staging Index y al Working Directory el resultado de eliminar al estado actual solamente los cambios que introdujo el commit de referencia. Si en el log hay otros commits después de la referencia, sus cambios no se eliminan. Si ves que el resultado no es lo que necesitas, puedes ejecutar `git revert --abort` para descartarlo todo.
git revert [-n|--no-commit] <ref-C> <ref-B> <ref-A>  // Revertir más de un commit. IMPORTANTE: indicarlos en orden descendiente (primero deshará el que esté más cerca del HEAD, "<ref-C>" en este ejemplo).
git revert [-n|--no-commit] HEAD~3..HEAD             // Revertir más de un commit consecutivo. En este ejemplo los 3 últimos commits.
git revert HEAD                                      // Crea un nuevo commit al final de la rama invirtiendo los cambios introducidos por el último commit (HEAD).
```


### Opciones de `git revert` <a name="opciones-de-git-revert"></a>

- **`-e | --edit`**

  Es la opción por defecto y no hace falta especificarla.

  Abre el editor para que puedas escribir el mensaje del commit. 

- **`--no-edit`**

  Es lo contrario a la anterior: no abrir el editor.

- **`-n | --no-commit`**

  No crea un nuevo commit.
  
  Solo añade al Staging Index y al Working Directory el resultado de invertir los cambios.
  
  Si ves que no es lo que necesitas, puedes ejecutar `git revert --abort` para descartarlo todo.


## Reset VS Checkout <a name="reset-vs-checkout"></a>

Tanto `git reset` como `git checkout` modifican los tres árboles, pero la manera de hacerlo por parte de `git checkout` es distinta dependiendo de si le indicas la ruta de un archivo o no.


### Primera diferencia: efectos en el Working Directory <a name="primera-diferencia-efectos-en-el-working-directory"></a>

- `git checkout`

  **Es seguro, porque antes de modificar el Working Directory se asegura de que no pierdas cambios recientes.**

  En realidad hace más que eso: intenta hacer un `merge` trivial en el Working Directory, de manera que todos los archivos que no has modificado los actualiza. Si hay cambios sin comitear directamente te avisa de que podrías perder información reciente y aborta el checkout con la siguiente sugerencia de hacer un `commit` o crear un `stash`:

  ```
  $ git s
  ## master
   M test33.md
  
  $ git checkout HEAD~
  error: Your local changes to the following files would be overwritten by checkout:
          test33.md
  Please commit your changes or stash them before you switch branches.
  Aborting
  ```

- `git checkout [<ref>] <file>`

  **No es seguro porque** no mueve el HEAD, sino que **actualiza el Staging Index para que ese archivo coincida con el estado que tiene en la referencia indicada y reemplaza directamente el archivo en el Working Directory, y pierdes los cambios recientes.**

  > Sería exactamente igual que un `git reset --hard [branch] <file>` si se pudiera ejecutar este comando (no se puede porque la opción `--hard` no está disponible con rutas de archivos. Da un error fatal: `"fatal: Cannot do hard reset with paths."`).

- `git reset --hard`

  **No es seguro porque directamente reemplaza todos los archivos del Working Directory sin comprobar nada previamente.**

- `git reset --soft <file>`

  NO EXISTE. Da un error fatal: `fatal: Cannot do soft reset with paths`.

- `git reset --hard <file>`

  NO EXISTE. Da un error fatal: `fatal: Cannot do hard reset with paths`.


### Segunda diferencia: efectos en el HEAD <a name="segunda-diferencia-efectos-en-el-head"></a>

Cómo actualizan el HEAD:

- `git reset` mueve la rama a la que apunta el HEAD, haciendo que la rama termine en el commit que se haya indicado y queden huérfanos los commits posteriores a `<ref>`, que acabarán siendo eliminados por el Garbage Collector.

- `git checkout` mueve el propio HEAD para que apunte a la otra rama. Es decir, se desplaza al final de la otra rama, pero la rama anterior queda intacta.

![Reset VS Checkout sobre el HEAD](https://git-scm.com/book/en/v2/images/reset-checkout.png)


### TABLA RESUMEN: Alcance de RESET y CHECKOUT <a name="tabla-resumen-alcance-de-reset-y-checkout"></a>

|                     | **HEAD** | **Index** | **Workdir** | **WD Safe?** |
| ------------------- | -------- | --------- | ----------- | ------------ |
| **Commit Level**            |
| `reset --soft [commit]`     | Mueve la rama a la que apunta el HEAD | NO | NO | YES |
| `reset [commit]`            | Mueve la rama a la que apunta el HEAD | YES | NO | YES |
| `reset --hard [commit]`     | Mueve la rama a la que apunta el HEAD | YES | YES | **NO** |
| `checkout <commit>`         | Mueve el propio HEAD para que apunte a la otra rama | YES | YES | YES |
| **File Level**              |
| `reset [commit] <paths>`    | NO | YES | NO | YES |
| `checkout [commit] <paths>` | NO | YES | YES | **NO** |

(Fuente: https://git-scm.com/book/en/v2/Git-Tools-Reset-Demystified)


### TABLA RESUMEN: Usos comunes y alcance de RESET, CHECKOUT y REVERT <a name="tabla-resumen-usos-comunes-y-alcance-de-reset-checkout-y-revert"></a>

| Command | Scope | Common use cases |
| ------- | ----- | ---------------- |
| `git reset` | Commit-level | Discard commits in a private branch or throw away uncommited changes |
| `git reset` | File-level | Unstage a file |
| `git checkout` | Commit-level | Switch between branches or inspect old snapshots |
| `git checkout` | File-level | Discard changes in the working directory |
| `git revert` | Commit-level | Undo commits in a public branch |
| `git revert` | File-level | (N/A) |

(Fuente: https://es.atlassian.com/git/tutorials/resetting-checking-out-and-reverting)


## Reset VS Revert <a name="reset-vs-revert"></a>

- El comando `git reset` **es peligroso, porque para devolver el proyecto al estado de un commit concreto necesita eliminar del historial todos los commits posteriores a la referencia indicada.**

  - **Lo más indicado es usarlo para deshacer cambios locales privados del Staging Index y del Working Directory que no hayan sido publicados.**

  - Surgen problemas cuando el reset se ejecuta en una rama compartida y esa rama se intenta subir al repositorio remoto con `git push`. En este escenario Git bloquea el `git push` debido a que a la rama que se intenta subir está desfasada respecto a la rama remota porque le faltan commits.
  
- El comando `git revert` **es 100% seguro**, porque **solamente deshace los cambios que ha introducido un commit concreto** (aunque es posible pasarle varios, o una referencia del tipo HEAD~3) **creando un nuevo commit al final de la rama sin eliminar ningún commit posterior a la referencia indicada, ni descartando los cambios introducidos por los commits posteriores.**
  
  - **Es el método más adecuado cuando se trabaja con repositorios públicos compartidos**, porque **no elimina ningún commit del historial** y entonces no da problemas cuando otros participantes suben cambios a la rama modificada.


# Resumen de acciones no recomendadas porque seguro que perderás tu trabajo del Working Directory y/o commits del historial <a name="resumen-de-acciones-no-recomendadas-porque-seguro-que-perderas-tu-trabajo-del-working-directory-y-o-commits-del-historial"></a>

- Ante la duda, siempre guarda el trabajo actual en un nuevo stash o en un nuevo commit, pero nunca hagas un reset y/o un checkout irrevertible de un archivo.

- Los únicos lugares donde los archivos están realmente a salvo son:

   - Stash

   - Commit (creado en la rama actual o en una nueva)
   
- Tener los archivos en el Staging Index no es ninguna garantía, porque con un `git reset --mixed` o `--hard` y/o con un `git checkout <ref> -- <file-name>` los cambios locales de los archivos que hay en el Working Directory y/o en el Staging Index se perderían al instante de manera irreversible.

```php
git checkout <ref> <path>                // Perderías tus cambios locales no guardados.

git reset --soft <ref>                   // Elimina del log los commits posteriores al de la referencia (realmente los deja huérfanos y posteriormente serán eliminados por el Garbage Collector).
git reset --mixed <ref>                  // Elimina del log los commits posteriores al de la referencia (realmente los deja huérfanos y posteriormente serán eliminados por el Garbage Collector).
git reset --hard <ref>                   // Elimina del log los commits posteriores al de la referencia (realmente los deja huérfanos y posteriormente serán eliminados por el Garbage Collector). Además elimina por completo los cambios locales sin guardar. Lo único que no elimina son los archivos nuevos que no hayas llegado añadir al Staging Index, porque solo reemplaza todos aquellos archivos que estén en seguimiento. Es mejor usar "git revert".

git commit --amend                       // Elimina el último commit de la historia y lo reemplaza por el nuevo que contiene la corrección del mensaje del commit y/o los archivos modificados o nuevos respecto al commit amendado. NO SE DEBE USAR EN REPOSITORIOS PÚBLICOS COMPARTIDOS, porque puede generar conflictos de fusión muy difíciles de solucionar.
git commit --amend -m "<nuevo-mensaje>"  // Mismas consideraciones que el anterior pero no abre el editor porque solo te permite escribir una línea.
git commit --amend --no-edit             // Mismas consideraciones que el anterior pero sin modificar el mensaje.

git rebase                               // Reescribe los commits con nuevos códigos SHA-1.  NO SE DEBE USAR EN REPOSITORIOS PÚBLICOS COMPARTIDOS

git clean -f                             // Elimina los archivos del Working Directory que no están en seguimiento.
git clean -df                            // Elimina los archivos del Working Directory que no están en seguimiento, incluídos los directorios.
git clean -xf                            // Elimina los archivos del Working Directory que no están en seguimiento, incluídos los ignorados.
git clean -dxf                           // Elimina los archivos del Working Directory que no están en seguimiento, incluídos los directorios y los ignorados.
```


# Ramas <a name="ramas"></a>

**Qué es una rama y qué ocurre cuando se elimina**

Si tomamos como referencia el grafo del log que se muestra al ejecutar `git log --oneline --decorate --all --graph`, puede parecer que una rama solo contiene los commits generados en ella a partir del commit de su creación (*fork*), y/o que si eliminas una rama de la que penden otras ramas vas a eliminarlas todas en cascada como ocurriría si talaras una gran rama de un árbol de verdad. Pero en Git no es así.

Una rama está definida por todos los commits que existen en el log siguiendo el recorrido desde su punta hasta el primer commit de la rama MASTER, que es desde donde parten todas las ramas del repositorio (para comprobarlo ejecuta `git log <branch>`). De modo que cuando eliminas una rama, como puede ser que haya commits que se estén compartiendo, solo se pueden llegar a eliminar los commits generados después de su *fork*, y siempre y cuando no los esté compartiendo con otras ramas (este detalle es el más relevente).

Por ejemplo, si se ha creado una nueva rama a partir de la rama master, al eliminar la nueva rama no se eliminan los commits de la rama master previos al *fork*, sino los que solamente forman parte de su historia (los posteriores al *fork*).

Esto es fácil de deducir porque con un árbol de verdad ocurriría lo mismo. Pero es que con los commits posteriores a su *fork* ocurre exactamente lo mismo, porque se les aplica la misma lógica con respecto a otras posibles ramas que se puedan haber creado a partir de ella. Es decir, si se han creado uno o varios *forks* (ramas) a partir de una rama desde un mismo commit o desde commits distintos, nunca se eliminarán aquellos commits que formen parte de la historia de las nuevas ramas, respectivamente. Únicamente se perderán los commits que estén por encima del último *fork* creado a partir de ella, porque ninguna otra rama dependerá de ellos.

Dicho de otra manera: cuando se elimina una rama derivada, como máximo se llegan a eliminar los commits posteriores a su *fork*. Pero si de la rama que se pretende eliminar se han creado otros *forks*, entonces solo se eliminan los commits posteriores al último *fork* (puede ser que solo haya un *fork* debido a que todas las ramas derivadas compartan el mismo), si es que hay commits posteriores.

CONCLUSIÓN

Sí que puedes eliminar una rama de la que has hecho uno o varios *forks* para crear una o varias ramas alternativas sin miedo a perderlas, porque eliminando la primera rama solo eliminas sus commits posteriores al *fork* que inicia la segunda. Y sus commits anteriores al *fork* no se eliminan porque siguen formando parte de la historia de la segunda rama (sin cambiar su referencia SHA-1 en el log).

Incluso si has creado un *fork* de master, es posible eliminar la rama master con `git branch -d master`. Si solo existe la rama master entonces no la puedes eliminar porque el repositorio tiene que tener como mínimo una rama.

Por último, recordarte que siempre y cuando conserves el SHA-1 y recuerdes el nombre de la rama eliminada, podrás recuperarla con `git checkout -b <branch-name> <sha-1>`.

```php
// VER
git branch                                     // Ver todas las ramas locales.
git branch -a                                  // Ver todas las ramas locales y remotas.
git branch -v                                  // Ver todas las ramas locales y remotas con el último commit de cada una (SHA-1 y mensaje).
git branch -vv                                 // Muestra todas las ramas y si tienen configurada alguna "upstream branch", cuántos commits por delante y por detrás están respecto a ellas (si no sale esta información significa "up-to-date"), y el SHA-1 y el mensaje del último commit.

// FILTROS
git branch [-v] --merged [<ref>]               // Ver todas las ramas que ya han sido mergeadas (sin asterisco) con la rama en la que te encuentras actualmente (con asterisco). Generalmente éstas ya se podrían eliminar con "git branch -d <branch-name>", porque se ha incorporado su trabajo a otra rama y no se va a perder nada. Si se indica un commit o el nombre de otra rama como argumento, entonces es posible ver esta misma información en relación a esa referencia sin necesidad de hacer previamente un "git checkout <ref>" para moverte a ella.
git branch [-v] --no-merged [<ref>]            // Ver todas las ramas que todavía no han sido mergeadas (todas están sin asterisco) con la rama en la que te encuentras actualmente y que, generalmente, convendrá no eliminar porque se perderá todo su trabajo. Si se intentan eliminar con "git branch -d <branch-name>" fallará. Pero se pueden eliminar con "git branch -D <branch-name>". Si se indica un commit o el nombre de otra rama como argumento, entonces es posible ver esta misma información en relación a esa referencia sin necesidad de hacer previamente un "git checkout <ref>" para moverte a ella.

// CREAR
git branch <branch-name>                       // Crea una nueva rama a partir del HEAD de la rama actual.

// CREAR Y CAMBIAR A ELLA
git checkout -b <branch-name>                  // Crea una nueva rama a partir del HEAD de la rama actual y mueve el HEAD a ella directamente.
git checkout -b <new-branch> <existing-branch> // Crea una nueva rama a partir del commit y/o nombre de rama que le indiques (aunque no estés ahí) y mueve el HEAD a ella directamente. Al indicar una referencia, este comando también lo puedes ejecutar estando en otra rama que no sea la base del nuevo fork.

// RENOMBRAR
git branch -m <new-branch-name>                   // Si estás en la rama que quieres renombrar
git branch -m <old-branch-name> <new-branch-name> // Si estás en otra rama

// ELIMINAR
git branch -d <branch-name>                    // Elimina la rama si ya ha sido mergeada con el HEAD de la rama actual en la que te encuentras y/o con la rama "upstream" (si es que hay alguna); sino te avisa y no la elimina para que no pierdas ningún commit. (Fuente: https://stackoverflow.com/questions/7548926/git-and-the-branch-x-is-not-fully-merged-error/27427237#27427237).
git branch -D <branch-name>                    // Elimina la rama aunque no haya sido mergeada.

// RECUPERAR
git checkout -b <branch-name> <sha1>           // Recupera una rama eliminada a partir de su nombre y SHA-1. Si no sabes el SHA-1 de la punta de la rama lo puedes consultar con "git reflog".

/* 
 * (Fuente: https://confluence.atlassian.com/bbkb/how-to-restore-a-deleted-branch-765757540.html)
 * 
 * If your commits are not in your reflog:
 *   1- You can try recovering a branch by reseting your branch to the sha of the commit found using a command like: 
*/
git fsck --full --no-reflogs --unreachable --lost-found | grep commit | cut -d\  -f3 | xargs -n 1 git log -n 1 --pretty=oneline > .git/lost-found.txt

// 2- You can then display each commit using one of these: 
git log -p <commit>
git cat-file -p <commit>
```

> **Consumo de recursos de las ramas**
> 
> **Because a branch in Git is actually a simple file that contains the 40 character SHA-1 checksum of the commit it points to, branches are cheap to create and destroy.** Creating a new branch is as quick and simple as writing 41 bytes to a file (40 characters and a newline).
> 
> This is in sharp contrast to the way most older VCS tools branch, which involves copying all of the project’s files into a second directory. This can take several seconds or even minutes, depending on the size of the project, whereas in Git the process is always instantaneous. Also, because we’re recording the parents when we commit, finding a proper merge base for merging is automatically done for us and is generally very easy to do.
> 
> (Fuente: https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell)


## Operaciones con ramas: `merge` y `rebase` <a name="operaciones-con-ramas-merge-y-rebase"></a>

- El comando `git merge` une los extremos de dos ramas en la rama base.

- Según la complejidad de la unión, el merge puede resolverse mediante **_fast-forward_** o por **_3-way merge_**. Este último puede ser de dos tipos: **_recursive strategy_** si es posible la unión automática; o **manual** en el caso de haber algún conflicto. ([Ver tipos de merge](#tipos-de-merge)).

  - **Consideraciones previas a un merge** para evitar que surjan conflictos que deban ser resueltos manualmente (o al menos minimizarlos) y se pueda realizar la unión por el sistema de *fast-forward* o *recursive strategy* (unión automática):

    - Debes asegurarte que estás en la punta de la rama (`git checkout <brnach-name>`).

    - Debes asegurarte que tanto la rama base (en la que se producirá el merge) como la rama a mergear están completamente actualizadas con los últimos commits remotos:
     
      - `git fetch`
      - `git merge` (o `git pull`)

    (Fuente: https://es.atlassian.com/git/tutorials/using-branches/git-merge)

  ```php
  git merge <rama>                        // Une los extremos de dos ramas en la rama actual. Se debe ejecutar desde la rama donde quieres que se produzca el merge. Combina los commits de ambas ramas. Según la complejidad de la unión, el merge puede resolverse por: "fast-forward", "recursive strategy" o, si hay conflictos, manualmente.
  git merge --no-ff <branch>              // Es igual que "git merge <rama>", pero siempre genera un merge commit, incluso cuando se ha resuelto por "fast-forward". Es muy útil cuando quieres documentar todos los merges que ocurren en tu repositorio.

  git merge <base> <branch>               // Une la rama <branch> en la rama <base>.
  
  git merge-base <feature-branch> <base>  // Solamente muestra el SHA-1 completo del commit usado como base de la "feature-branch". Es decir, a partir de qué commit se creó la rama (fork). NO UNE LAS DOS RAMAS INDICADAS.
  ```

- El comando `git rebase` en su **modo estándar** (`git rebase <base>`) reproduce los cambios de una rama en otra en el orden que sucedieron originalmente. En su **modo interactivo** (`git rebase -i <base>`) permite realizar muchas otras operaciones con los commits de una rama. Más información sobre estos modos en [MERGE VS REBASE](#merge-vs-rebase).

  ```php
  git rebase <base>                       // Rebases the current branch onto <base>, which can be any kind of commit reference (for example an ID, a branch name, a tag, or a relative reference to HEAD).
  git rebase <base> <feature-branch>      // Rebases the <feature-branch> onto <base>, which can be any kind of commit reference (for example an ID, a branch name, a tag, or a relative reference to HEAD).
  git rebase -i <base>                    // Rebases the current branch onto <base> but uses an interactive rebasing session. Proporciona un control mucho más exhaustivo sobre las modificaciones del historial que el "git rebase" estándar. Es SEGURO, porque si tienes cambios sin guardar te avisa con este mensaje: "Cannot rebase: You have unstaged changes. Please commit or stash them.".
  git rebase --continue                   // Estando en una sesión de rebase interactiva, permite indicar que queremos continuar hasta el siguiente commit cuando ya hemos hecho los cambios que queríamos en el commit actual.
  ```


### Tipos de merge <a name="tipos-de-merge"></a>

- **"Fast-forward"** <a name="merge-tipo-fast-forward"></a>

  - **Sucede cuando se crea una nueva rama desde el HEAD de la rama base y solo avanza la nueva rama.**
  
  - Los commits de la nueva rama solo introducen cambios que no entran en conflicto con ningún archivo de la rama base.
  
  - Los cambios se integran directamente a la rama base porque no hay conflictos.

  - Cada uno de los commits de la rama mergeada pasan a formar parte de la rama base con los mismos códigos SHA-1 y en el mismo orden.
  
  - **Aplana el historial de las dos ramas**, es decir:
  
    - La rama mergeada se integra totalmente en la rama base y sigue existiendo, pero ya no como un *fork* de la rama base.
      
      Si consultas los commits que la rama mergeada generó desde su *fork* verás que ya no muestra ningún registro porque ya no existe ese *fork*:
      
      ```
      git log <base>..<feature-branch> --oneline
      ```
    - La rama mergeada ahora es idéntica a la rama base.
    
      Si consultas los commits de cada rama verás que comparten exactamente los mismos:
      
      ```
      git log <base> --oneline
      git log <feature-branch> --oneline
      ```
      
  - La rama mergeada no se elimina. Se tiene que eliminar manualmente.

- **"3-way merge"** <a name="merge-tipo-3-way-merge"></a>

  Se llama así porque Git usa el commit de la punta de cada rama y el commit donde se produce el *fork* entre ambas ramas para ver lo que ha avanzado cada una. En total son 3 commits. El commit de tipo *3-way* es especial porque tiene dos commits padres (las puntas de las ramas) en lugar de uno, que es lo habitual.

  **Sucede cuando se crea una nueva rama desde el HEAD de la rama base y las dos ramas han avanzado.**

  Es muy habitual en ramas que concentran un desarrollo muy largo. Debido al tiempo que llega a transcurrir hasta que se finaliza la nueva característica, es normal que en la rama base también se lleguen a crear nuevos commits y que, en el momento de hacer el merge, se tengan que contrastar los cambios de ambas ramas para determinar si hay conflictos. Esta operación la realiza internamente Git, dando lugar a dos posibles situaciones, tal como se describe a continuación.

  > A veces, cuando la rama a mergear es muy corta, para evitar que se genere el commit adicional de unión característico del *3-way merge*, [puede convenir hacer un `git rebase`](#merge-vs-rebase) en la punta de la rama base para aplanar el historial de ambas ramas. Después de hacer el `git rebase`, el `git merge` que hay que ejecutar a continuación se resuelve con *Fast-forward*.

  **Un *3-way merge* puede dar lugar a dos posibles situaciones:**

  - **Unión automática** (**_recursive strategy_**)

    - Git crea en la rama base un nuevo commit de tipo *3-way merge* para unir las dos ramas, porque a pesar de que hay cambios en ambas ramas, detecta que no se solapan. Como no modifican las mismas líneas, no hay conflictos y el merge se puede realizar sin problemas por medio de la estrategia recursiva.
    
      > *Merge made by the 'recursive' strategy.*

    - La rama mergeada no se elimina. Se tiene que eliminar manualmente.

    <a name="informacion-sobre-la-ramificacion-creada-por-un-three-way-merge"></a>
    - Aunque se elimine la rama mergeada, en el grafo de `git log` se sigue viendo esa ramificación porque ahora sus commits también pertenecen a la rama base. Esa ramificación se inicia en el fork de la rama mergeada y se une a la rama base en el commit del *3-way merge*.
    
      Se puede observar como siempre que se hace un *3-way merge*, los commits aparecen ordenados en el grafo de la siguiente manera, independientemente de si se han creado antes los de la rama mergeada o los de la rama base**:
      
      1. PRIMERO los commits de la rama base (porque siempre tienen preferencia), y en su orden original. Si te fijas, su asterisco `*` está en la línea de la rama base. En la ramificación solo tienen una raya `|`.
      
      2. DESPUÉS los commits de la rama mergeada, y en su orden original.  Si te fijas, son los que tienen el asterisco `*` en la línea de la rama mergeada. En la rama base solo tienen una raya `|`.
      
      **Ejemplo:**

      ```
      +------------------------------------------+--------------------------------------------------------+--------------------------------------------------------+
      |    ANTES DEL MERGE                       |   DESPUÉS DEL MERGE                                    |   DESPUÉS DE ELIMINAR LA RAMA MERGEADA                 |
      +------------------------------------------+--------------------------------------------------------+--------------------------------------------------------+
      |                                          |     *   0e4e42c (HEAD -> master) Merge branch 'ramaE'  |     *   0e4e42c (HEAD -> master) Merge branch 'ramaE'  |
      |                                          |     |\                                                 |     |\                                                 |
      |    * a9a3601 (HEAD -> master) Updated B  |     | * 36f81c1 (ramaE) Updated E                      |     | * 36f81c1 Updated E                              |
      |    | * 36f81c1 (ramaE) Updated E         |     | * ca57ad2 Added E                                |     | * ca57ad2 Added E                                |
      |    | * ca57ad2 Added E                   |     * | a9a3601 Updated B                              |     * | a9a3601 Updated B                              |
      |    |/                                    |     |/                                                 |     |/                                                 |
      |    * 76f6d8f Updated D                   |     * 76f6d8f Updated D                                |     * 76f6d8f Updated D                                |
      |    * a7c6fd2 Added D                     |     * a7c6fd2 Added D                                  |     * a7c6fd2 Added D                                  |
      +------------------------------------------+--------------------------------------------------------+--------------------------------------------------------+
      ```
      
      Tal como se ve en la primera columna, **en este ejemplo se han creado primero los commits de la rama mergeada**, pero eso no hace que después del merge visualmente sigan apareciendo primero. Porque como ya se ha dicho, el orden que queda en el grafo después del merge es siempre el mismo: primero van los de la rama base (sea la cantidad que sea) y, por encima de ellos, los de la rama mergeada.

      Esto ocurre simplemente para que sea más fácil distinguir que los commits que pertenecían a la rama mergeada son los que se han unido a la rama base.

      El último commit de la ramificación es la punta de la rama mergeada, como siempre. **Si se elimina la rama mergeada** simplemente desaparece su nombre de ese commit dejando de indicar que era su punta; pero **la ramificación permanecerá para siempre porque ahora también es parte de la historia de la rama base.**

      **Por último aclarar que, aunque visualmente pueda parecer que dentro de esta ramificación están los commits con los cambios de las dos ramas** (porque la información aparece a la derecha alineada al mismo nivel), y que la rama mergeada ("ramaE") tiene como punta su último commit (36f81c1), **no quiere decir que el commit que hubo en la rama base** (master) después del *fork* (a9a3601) antes de producirse el *3-way merge* **ahora pertenezca a la rama mergeada.** Esto lo podemos comprobar consultando los commits que definen a cada rama con `git log <branch> --oneline` como se muestra en el cuadro de más abajo.

      Además, en los siguientes listados se puede ver como los commits de cada rama aparecen exactamente en el orden que sucedieron en la historia, indistintamente de la rama a la que pertenecían originalmente. Es decir, no aparecen siempre primero los de la rama base como ocurre en el grafo del `git log` del ejemplo anterior (en este caso "primero" implicaría estar "más abajo" en la lista por ser más antiguos). Esto es lógico, porque como ya se ha comentado, el grafo los coloca de esa manera solo para que sea más fácil distinguir qué commits eran de la rama base y cuáles de la rama mergeada. Pero a la hora de mostrar el historial de una rama siempre respeta el orden real en el que sucedieron los commits, sin más consideraciones, como no podía ser de otra manera.

      **Resultado del `git log` de cada rama del ejemplo anterior después del merge:**
      
      ```
      +---------------------------------------------------+--------------------------------+
      |   `git log master --oneline`                      |   `git log ramaE --oneline`    |
      +---------------------------------------------------+--------------------------------+
      |    0e4e42c (HEAD -> master) Merge branch 'ramaE'  |                                |
      |    a9a3601 Updated B                              |                                |
      |    36f81c1 (ramaE) Updated E                      |   36f81c1 (ramaE) Updated E    |
      |    ca57ad2 Added E                                |   ca57ad2 Added E              |
      |    76f6d8f Updated D                              |   76f6d8f Updated D            |
      |    a7c6fd2 Added D                                |   a7c6fd2 Added D              |
      +---------------------------------------------------+--------------------------------+
      ```

  - **Unión con resolución manual de conflictos**
  
    - Git detecta conflictos al haber cambios entre ambas ramas que modifican las mismas líneas y no puede resolver la situación de manera automática. Por lo tanto te avisa para que revises los conflictos manualmente y decidas qué cambios hay que preservar en cada archivo porque consideras que son los buenos.

      Git finaliza el merge cuando resuelves todos los conflictos y subes al Staging Index los archivos que quieres y confirmas los cambios ejecutando `git commit` (o ejecutando `git commit -am "<mensaje>"` si quieres hacerlo todo a la vez; pero este comando incluirá todos los archivos en seguimiento).
      
      No tienes que ejecutar de nuevo `git merge`, porque mientras resuelves los conflictos sigues estando con el proceso del primer `git merge` abierto. Lo puedes comprobar en el propio *bash*: si te fijas en la línea que muestra tu usuario de ordenador y el directorio en el que te encuentras, al final aparece entre paréntesis `(<nombre-rama>|MERGING)`. Esta información también aparece cuando estás en una sesión de [rebase interactivo](#merge-vs-rebase): `(<nombre-rama>|REBASE-i <num-commit>/<num-total-commits-rebased>)`.

      > **Cómo saber qué archivos están en conflicto**
      > 
      > Como Git usa el flujo de trabajo habitual para resolver los conflictos de merge (es decir: editar los archivos, subirlos al Staging Index con `git add` y confirmar los cambios revisados con `git commit`), puedes ejecutar el comando `git status` para ver qué archivos tienes que revisar.

    - La rama mergeada no se elimina. Se tiene que eliminar manualmente.

    - Aunque se elimine la rama mergeada, en el grafo de `git log` se sigue viendo esa ramificación porque ahora sus commits también pertenecen a la rama base. Esa ramificación se inicia en el fork de la rama mergeada y se une a la rama base en el commit del *3-way merge*.
    
      > Todo lo que se pueda decir de esta ramificación es exactamente igual a como ocurre en la **Unión automática** ([ver la explicación y el ejemplo de más arriba](#informacion-sobre-la-ramificacion-creada-por-un-three-way-merge)).

(Fuente: https://es.atlassian.com/git/tutorials/using-branches/git-merge)


### MERGE VS REBASE <a name="merge-vs-rebase"></a>

Si después de haber creado una `feature-branch` a partir de la rama `master`, por ejemplo, la rama `master` contiene nuevos commits, tienes 2 opciones para incorporar sus cambios a la `feature-branch` para tenerla al día: hacer un **merge** o un **rebase**.

- Con `git merge`, por cada incorporación de los cambios del nivel superior a la rama `feature-branch` crea un nuevo commit de fusión ([*3-way merge*](#merge-tipo-3-way-merge)) innecesario.

- Con `git rebase` se mueve el inicio de la `feature-branch` al último commit de la rama `master` como si se hubiera creado desde el HEAD actual. Y cuando se hace el merge el resultado es un historial mucho más limpio, porque aplana los commits de las dos ramas en la rama base en lugar de generar un nuevo commit de fusión (*3-way merge*).

  No siempre se puede resolver el merge con [*fast-forward*](#merge-tipo-fast-forward). También puede ser que surjan conflictos durante un `git rebase`. En ese caso se tendrían que resolver manualmente y luego ejecutar `git rebase --continue` para continuar.

  **Desventajas**:
  
  - Pierdes la trazabilidad, porque no puedes saber cuándo has incorporado los cambios de nivel superior.

  - Al reorganizar los commits reescribe el historial del proyecto, creando así nuevos commits para cada commit de la `feature-branch`.
  
  - Reescribir el historial del proyecto puede tener consecuencias catastróficas para el *workflow* de colaboración si no se sigue la **"regla de oro de la reorganización": no usar `git rebase` jamás en ramas públicas.**



**El comando `git rebase` tiene 2 modos:**

- **Modo estándar (`git rebase <base> [<feature-branch>]`):**

   - Cambia el origen de la rama actual (posición del *fork*) haciendo que parezca que la creaste desde el HEAD actual de la rama <base> indicada.

     Es decir, puedes mover el *fork* de la rama derivada tanto al HEAD actual de la rama base original (desplazamiento lineal), como al HEAD de una nueva rama (desplazamiento a otra rama).
     
     <base> puede ser cualquier referencia válida: SHA-1, nombre de rama, posición relativa al HEAD, etc.

   - **Internamente Git crea nuevos commits aplicados a la nueva base para lograrlo. Por este motivo no se debe usar `git rebase` en commits que se han hecho públicos, o parecerá que el historial de tu proyecto ha desaparecido al haber reemplazado los commits viejos por unos nuevos.**

   - Aunque la rama parezca la misma, es importante entender que se compone de commits totalmente nuevos.

   - **Motivo principal para usarlo:** mantener una historia lineal del proyecto.
   
     A diferencia de cuando se unen dos ramas con `git merge`, con el modo estándar de `git rebase` no se crea un *merge commit* (*3-way merge*). Simplemente se trasladan a la punta de la rama base indicada todos sus commits y el historial queda lineal.

     Por eso es común usar rebase para integrar en tu repositorio local los últimos cambios del repositorio remoto "upstream", porque evitas tener en tu historial un *3-way merge* cada vez que te pones al día para saber cuánto ha progresado el proyecto. Es como decir: “Quiero basar todos mis cambios sobre lo que los demás ya han hecho”.
     
  - **Pasos para realizar un `git rebase`:**
  
    1. Moverte a la rama que quieres desplazar.

    2. Ejecutar `git rebase <base>` indicando el nombre de la rama base donde se crearán los nuevos commits.

    3. Cuando ha terminado, ejecutar `git checkout <base>` y luego `git merge <feature-branch>`, que hará un *fast-forward* (si no hay conflictos).
    
       > No siempre se puede resolver el merge con [*fast-forward*](#merge-tipo-fast-forward). También puede ser que surjan conflictos durante un `git rebase`. En ese caso se tendrían que resolver manualmente y luego ejecutar `git rebase --continue` para continuar.
       
       En este punto las dos ramas (`<base>` y `<feature-branch>`) quedan apuntando al último commit de la rama base.
       
       ![Basic rebase](https://git-scm.com/book/en/v2/images/basic-rebase-4.png)

    **Estos 3 pasos se pueden simplificar ejecutando `git rebase <base> <feature-branch>`.**

   - Después de hacer el rebase y el merge en la rama base puedes eliminar la otra rama con `git branch -d <feature-branch>` porque ya está integrada y no la necesitas más.

   - Hay una **versión más avanzada**:

     ```php
     git rebase --onto <new-base> <old-base> <feature-branch>
     ```
    
     **Ejemplo:**

     ```php
     o---o---o---o---o master
      \
        o---o---o---o---o featureA
         \
           o---o---o featureB
     ```
     
     featureB is based on featureA, however, we realize featureB is not dependent on any of the changes in featureA and could just be branched off  master.
 
     `git rebase --onto master featureA featureB`
 
     featureA is the `<oldbase>.` master becomes the `<newbase>` and featureB is reference for what HEAD of the `<newbase>` will point to. The results are then:
 
     ```php
      o---o---o featureB
     /
     o---o---o---o---o master
     \
      o---o---o---o---o featureA
     ```
     
     (Fuente: https://es.atlassian.com/git/tutorials/rewriting-history/git-rebase)
 

- **Modo interactivo (`git rebase -i <base>`):**

   - Se debe ejecutar estando en la rama que contiene los commits que quieres modificar. Si el nombre de la rama base es la actual, los cambios se harán ahí. Si eliges otra rama como base, se hará el *rebase* de la rama actual sobre la nueva referencia.

   - Es SEGURO, porque si tienes cambios sin guardar te avisa con este mensaje: `"Cannot rebase: You have unstaged changes. Please commit or stash them."`.

   - La opción interactiva `git rebase -i` proporciona un control mucho más exhaustivo sobre las modificaciones del historial que el `git rebase` estándar.
   
     Además de poder mover todos los commits de un rama a una nueva base, permite alterar commits individualmente durante el proceso de *rebase*. Es decir, permite detenerte en cada commit para decidir qué quieres hacer.

     Las acciones que permite aplicar por cada uno de los commits que participan en un rebase son:
     
     ```
     # p, pick   = use commit
     # r, reword = use commit, but edit the commit message
     # e, edit   = use commit, but stop for amending
     # s, squash = use commit, but meld into previous commit
     # f, fixup  = like "squash", but discard this commit's log message
     # x, exec   = run command (the rest of the line) using shell
     # d, drop   = remove commit
     ```

   - Al iniciar una sesión de rebase interactiva **Git crea una área temporal donde se ha movido el HEAD a la referencia indicada en <base>, dejando el log como si no hubieran más commits después de dicha referencia** (óbivamente, si se le pasa como referencia el valor `HEAD` no se apreciará esta circunstancia porque no habrá commits posteriores). Se puede comprobar ejecutando `git log` inmediatamente después del rebase.   
     
     Es decir, sucede algo parecido a cuando se hace un `git reset --hard <ref>`, solo que en este caso ocurre en una área temporal, y los commits posteriores (si los hay) realmente no se quedan huérfanos ni se eliminan.

   - **Internamente Git crea nuevos commits con un ID distinto a los commits originales. Los commits marcados con **`pick`** también tendrán un nuevo ID si los commits anteriores a ellos se han reescrito.**

   - Cuando inicias un `git rebase -i`, por cada commit en el que se detiene, Git te permite ejecutar los comandos que quieras, y te pide que cuando estés seguro de que ya no quieres hacer más modificaciones en un commit, ejecutes `git rebase --continue` para continuar con el siguiente commit.
   
     Por defecto Git te sugiere que hagas los cambios que creas oportunos en el commit, añadas los archivos modificados al Staging Index y luego ejecutes git commit --amend para hacerlos efectivos. Pero puede sucederte que no quieras amendar el commit porque no requiera cambios, sino que simplemente quieras subdividirlo en commits más pequeños, por ejemplo, y podrías hacerlo perfectamente. Es decir, nada te obliga a usar `git commit --amend`.

     A continuación se muestra un ejemplo en el que un commit no se amenda y simplemente se subdivide en dos commits independientes.
     
     En el ejemplo, la referencia que se le pasa a `git rebase` no es `HEAD` sino `HEAD~2`, de modo que el log termina dos commits antes del HEAD real de la rama, pero solo mientras dura la sesión de rebase. Como el HEAD ahora apunta a ese commit, al hacer el `git reset HEAD^` lo que se consigue es dejar el Staging Index y el HEAD como si todavía no se hubiera producido el commit usado como referencia del rebase. De modo que en ese punto se pueden añadir al Staging Index los archivos que se quieran y ejecutar `git commit`; y repetir este proceso tantas veces como nuevos commits se quieran introducir antes de los dos últimos commits del log que se han retrocedido. Esto es posible precisamente por lo que se ha dicho más arriba de que "Git te permite ejecutar los comandos que quieras"; realmente incluye todos los comandos, incluídos `git reset` y `git commit`.
     
     ```php
     git rebase -i HEAD~2

     // No queremos hacer cambios y ejecutar `git commit --amend` sobre el commit de la referencia indicada (HEAD~2) porque ya tenemos las modificaciones hechas. Solo queremos separar los cambios de este commit en dos commits más pequeños. Con lo cual hacemos lo siguiente:
     git reset HEAD^  // Dejamos el Staging Index y el HEAD como si todavía no se hubiera producido el commit en el que estábamos.

     // Ahora creamos commits independientes los dos archivos que se habían modificado en el commit original.
     git add README.md
     git commit -m "Actualización del README"

     git add EJEMPLO.md
     git commit -m "Actualización del EJEMPLO"

     git rebase --continue
     ```

   - Abre el editor para que elijas el tipo de comando que quieres aplicar a cada commit que va a participar en el *rebase*. Estos comandos determinan cómo se van a trasladar (y/o simplemente alterar) los commits individualmente a la base, que puede ser la actual o una nueva.

     **La lista contiene los commits en orden ascendente (arriba los más antiguos y abajo lo más recientes) porque siempre empieza a reescribir la historia desde el commit más antiguo.**
     
     Una vez especificado el comando a cada commit del rebase, Git empezará a tirar hacia atrás en el historial para aplicar el comando correspondiente a cada commit.

     Consideraciones sobre algunas acciones específicas:

     - **Si quieres reordenar commits** debes cambiar su orden cuando te muestra el listado de commits con el **`pick`** delante. Se trata simplemente de subir y/o bajar las líneas, no de cambiar el nombre del comando (`pick` por defecto).

       **IMPORTANTE: cuando Git reordena commits crea un nuevo código SHA-1 para cada commit pero no modifica su fecha original.**
       
       Esto puede causar aún más confusión a la hora de revisar los cambios, porque puede suceder que un commit más antiguo pase a estar por delante de otro más actual, provocando que no toda la historia del respositorio siga un orden cronológico.

     - **Si quieres eliminar commits** solo tienes que borrar las líneas correspondientes del listado de commits con el **`pick`** delante, o bien reemplazar la opción **`pick`** por **`d | drop`**.

   - **Si surjen conflictos de merge** tienes varias opciones:
   
     - **Resolver los conflictos manualmente**, luego añadir al Staging Index los archivos que quieras con `git add <file>` y/o eliminarlos con `git rm <file>`, y confirmar que has terminado con `git rebase --continue`.
     
     - **Saltarte el commit que presenta conflictos** con `git rebase --skip`.
     
     - **Abortar todo el rebase interactivo** con `git rebase --abort` para que se revierta la situación a como estaba todo antes de haberlo iniciado.

   - **Si has eliminado algún commit del log de una rama debido a un subcomando del rebase como `squash` o `drop`, puedes recuperarlos con `git reflog`.**

   - **No usar `git rebase` en commits que se han hecho públicos (estoy incluye Pull Requests enviados), o parecerá que el historial de tu proyecto ha desaparecido al haber reemplazado los commits viejos por unos nuevos.**
   
     Si otro colaborador lo ha hecho (habrá tenido que forzarlo con `git push --force`, sino no te deja debido a los conflictos que detecta), puedes usar `git pull --rebase` en lugar de `git pull` para intentar evitar los conflictos en tu copia del repositorio.

   - **Motivo para usarlo:** a muchos desarrolladores les gusta usar el rebase interactivo para pulir su rama de desarrollo personal antes de hacer el merge con la rama principal.
   
     Esto da la oportunidad de hacer un squash de commits insignificantes, eliminar commits obsoletos, y asegurarte de que todo está en orden antes de hacer el commit en la historia "oficial" del proyecto.
     
     Para los demás, parecerá como que has desarrollado tu nueva característica con la cantidad perfecta de commits a la primera.
     
     Aquí es donde el rebase permite mantener un historial limpio y conteniendo únicamente commits realmente significativos.

> **IMPORTANTE**
> 
> El comando `git rebase` crea nuevos códigos SHA-1.
> 
> La **opción** de **"Rebase and merge"** de **GitHub**, además de crear nuevos códigos SHA-1, **también actualiza la información del _commiter_** (autor de los cambios).

(Fuente: https://medium.com/@gabriellamedas/git-rebase-and-git-rebase-onto-a6a3f83f9cce)

(Fuente: https://es.atlassian.com/git/tutorials/rewriting-history/git-rebase)


### Opciones de `git rebase -i` <a name="opciones-de-git-rebase--i"></a>

```php
# Commands:
# p, pick = use commit
# r, reword = use commit, but edit the commit message
# e, edit = use commit, but stop for amending
# s, squash = use commit, but meld into previous commit
# f, fixup = like "squash", but discard this commit's log message
# x, exec = run command (the rest of the line) using shell
# d, drop = remove commit
```

- **`r | reword`**

  Detiene la reorganización y te permite reescribir el mensaje de un commit individual.

- **`s | squash`**

  Detiene la reorganización en cualquier commit marcado con la `s` y te pide editar los distintos mensajes de commit en un único mensaje combinado.

- **`e | edit`**

  Detiene la reorganización para que puedas aplicar los cambios que necesites (amend). Es también la opción a elegir cuando quieres dividir un commit en varios commits. Cuando Git se detiene en ese commit puedes hacer un `git reset HEAD^` para que te deshaga el commit y te deje los archivos fuera del Staging Index. Entonces puedes repetir tantas veces como necesites el proceso de añadir al Staging Index archivos y crear un commit. Una vez hayas terminado de subdividirlo en pequeños commits, debes continuar con `git rebase --continue`.


While these are the most common applications, `git rebase` also has **additional command options** that can be useful in more complex applications.

- **`git rebase -- d`** means during playback the commit will be discarded from the final combined commit block.

- **`git rebase -- p`** leaves the commit as is. It will not modify the commit's message or content and will still be an individual commit in the branches history.

- **`git rebase -- x`** during playback executes a command line shell script on each marked commit. A useful example would be to run your codebase's test suite on specific commits, which may help identify regressions during a rebase.

(Fuente: https://es.atlassian.com/git/tutorials/rewriting-history/git-rebase)



**RECOVERING FROM UPSTREAM REBASE**

If another user has rebased and force pushed to the branch that you’re committing to, a git pull will then overwrite any commits you have based off that previous branch with the tip that was force pushed. Luckily, using git reflog you can get the reflog of the remote branch. On the remote branch's reflog you can find a ref before it was rebased. You can then rebase your branch against that remote ref using the --onto option as discussed above in the Advanced Rebase Application section.

(Fuente: https://es.atlassian.com/git/tutorials/rewriting-history/git-rebase)

## Squashing <a name="squashing"></a>

Se puede hacer con `git reset` y con `git rebase -i`.

- Con `git reset`:
  
  https://git-scm.com/book/en/v2/Git-Tools-Reset-Demystified (Sección "Squashing")

- Con `git rebase -i`:
  
  https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History#_squashing


### Squashing con `git reset --soft` <a name="squashing-con-git-reset---soft"></a>

Al usar la opción `--soft` solo te actualiza el HEAD para que coincida con el de la referencia indicada, pero el Staging Index y el Working Directory siguen en el estado actual.

Si en este punto haces commit, estás consiguiendo unir tantos commits como hayas retrocedido en uno solo. Esto si consideramos el escenario en el que durante esa sucesión de commits solo has modificado y/o añadido archivos que sigues teniendo en tu Working Directory.

Si en algún commit se hizo algún cambio más complejo con `git reset <ref> <file>`, por ejemplo, y no todo fueron cambios lineales, entonces estás haciendo un salto de cambios directo desde el commit de referencia hasta tu estado actual sin considerar esas otras variaciones particulares que se hubieran podido producir en los commits del medio (los que has dejado huérfanos al hacer el reset).

CONCLUSIÓN

Como en cualquier reset, **solo es conveniente ejecutarlo si estás muy seguro de lo que estás haciendo.**

```php
git reset --soft <ref>

// Squash de los 2 últimos commits.
git reset --soft HEAD~2
git commit
```


### Squashing con `git rebase -i` <a name="squashing-con-git-rebase--i"></a>

Una vez ejecutado el `git rebase -i` se abre el editor. Especifica el comando `s | squash` en los commits individuales que quieres unir. Se unirán al commit que tenga el comando `pick`.

**Ejemplo:**

```php
pick ...
pick ...
pick ...
squash ...  // Este commit se unirá al de arriba.
```

**El orden de los commits que aparece cuando se abre el editor es ascendente** de más antiguo (el primero) a más reciente (el último). Arriba está el más antiguo porque es por el que empezará a hacer el rebase.


## Cherry-pick <a name="cherry-pick"></a>

- El comando `git cherry-pick` te permite **copiar** (no trasladar) en la rama en la que te encuentras los cambios que han introducido uno o varios commits que pertenecen a otra rama.

  Por ejemplo, si estás en el último commit ("H") de una subrama y ejecutas `git cherry-pick E`, siendo "E" un commit de otra rama, le estás indicando a Git que copie los cambios que introdujo "E" y que los aplique sobre "H", creando una E prima ("E'") en la subrama.

- Puedes ejecutar este comando con varios commits también. Por ejemplo: `git cherry-pick C D E`.

- Los cambios los aplica cronológicamente tal como sucedieron realmente en la rama de donde los estás copiando. Es decir, en orden ASCENDENTE: de más antiguos a más recientes.

(Fuente: http://think-like-a-git.net/sections/rebase-from-the-ground-up/using-git-cherry-pick-to-simulate-git-rebase.html)


## Cómo recuperar una rama eliminada <a name="como-recuperar-una-rama-eliminada"></a>

Es posible recuperar una rama eliminada a partir de su nombre y `SHA-1`. Si no sabes el `SHA-1` de la punta de la rama lo puedes consultar con `git reflog`.

```php
git checkout -b <branch-name> <sha1>  // Recupera una rama eliminada a partir de su nombre y SHA-1. Si no sabes el SHA-1 de la punta de la rama lo puedes consultar con "git reflog".
```

## Reescribir ramas (aplicar una acción en todos los commits del log) <a name="reescribir-ramas-aplicar-una-accion-en-todos-los-commits-del-log"></a>

> **Puedes ver toda la información en el manual local de Git** ejecutando el siguiente comando:
> 
> ```
> git filter-branch --help
> ```
> 
> El manual se ubica en:
> 
> ```
> file:///C:/Program%20Files/Git/mingw32/share/doc/git-doc/git-filter-branch.html
> ```
> 


Casos donde `git filter-branch` es de gran ayuda:

- Eliminar un archivo de todos los commits.

- Hacer que un subdirectorio sea la nueva raíz del proyecto para cada commit.

- Cambiar el email de todos tus commits.

```php
git filter-branch --tree-filter '<action>' HEAD             // Ejecuta la acción en todos los commits de la rama actual y recommitea los resultados.
git filter-branch --tree-filter 'rm -f <file>' HEAD         // Elimina el archivo <file> de todos los commits de la rama actual, lo tengan o no (la opción "-f" evita que salte un error si el archivo no se encuentra en el árbol de un commit).
git filter-branch --tree-filter 'rm -f passwords.txt' HEAD  // Elimina el archivo "passwords.txt" de todos los commits de la rama actual, lo tengan o no.
git filter-branch --tree-filter 'rm -f *~' HEAD             // Elimina todos los archivos de backup del editor de la rama actual.
git filter-branch --tree-filter --all '<action>' HEAD       // Ejecuta la acción en todos los commits de todas las ramas y recommitea los resultados.
```

Si quieres reemplazar el email, por ejemplo, debes tener cuidado con reemplazar solo el tuyo. Para conseguirlo usa la opción `--commit-filter`:

```php
// This goes through and rewrites every commit to have your new address. Because commits contain the SHA-1 values of their parents, this command changes every commit SHA-1 in your history, not just those that have the matching email address.

$ git filter-branch --commit-filter '
        if [ "$GIT_AUTHOR_EMAIL" = "schacon@localhost" ];
        then
                GIT_AUTHOR_NAME="Scott Chacon";
                GIT_AUTHOR_EMAIL="schacon@example.com";
                git commit-tree "$@";
        else
                git commit-tree "$@";
        fi' HEAD
```
(Fuente: https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History#_changing_email_addresses_globally)


# Tags <a name="tags"></a>

Conviene crear un tag por cada `git push` que hagamos a la rama de producción.

```php
git tag                                   // Ver lista de tags
git tag <name>                            // Crear tag "lightweight"
git tag -a <name> [ref] [-m "<message>"]  // Crear tag "anotado". La referencia y el mensaje son opcionales. Si no se especifica la opción "-m" se abre el editor para que puedas escribir un mensaje más elaborado.
git tag -d <name>                         // Eliminar tag
git tag -n                                // Ver todos los tags con su mensaje
git tag <name> -n                         // Ver mensaje del tag especificado
git tag <name> -n99                       // Ver las primeras 99 líneas del mensaje del tag especificado

// REPOSITORIO REMOTO
git push --tags          // Sube todos los tags al repositorio remoto. IMPRESCINDIBLE después de subir un repositorio a GitHub, porque los tags no se suben automáticamente; hay que hacerlo manualmente. NO ES RECOMENDABLE SUBIRLOS SIEMPRE TODOS. Después de haberlos subidos todos por primera vez luego es mejor usar "git push <remote> <tag>" para evitar subir tags antiguos malos.
git push <remote> <tag>  // Sube al repositorio remoto solo el tag especificado. Es la OPCIÓN RECOMENDADA, porque si siempre usas "git push --tags" podrías estar subiendo tags antiguos malos.
git push origin <tag>    // Sube al repositorio remoto "origin" solo el tag especificado.
```


## Cómo nombrar las versiones <a name="como-nombrar-las-versiones"></a>

http://www.semver.org

v1.0.0
vCambioMayor.cambioMenor.parche


# Cómo guardar tu trabajo cuando está a medias y no quieres perderlo (`stash`) <a name="como-guardar-tu-trabajo-cuando-esta-a-medias-y-no-quieres-perderlo-stash"></a>

- **No puedes crear un primer stash hasta que no exista un primer commit.**

  Es lógico, porque un stash sirve para guardar el estado de tu proyecto cuando no quieres perder los últimos cambios que todavía no has comiteado antes de moverte a otra rama, commit o cualquier otra referencia (otro stash, un tag, una release, etc.). Si el repositorio es tan reciente no tiene senido esta acción, por eso no lo permite.

  Al iniciar el repositorio, cuando creas nuevos archivos debes añadirlos al Stage, sino te avisa de que no hay nada nuevo para crear un stash. Esto ocurre porque hasta que no están en el Staging Index Git no les está haciendo ningún seguimiento (están con el código de estado `U` de *untracked*).

- **Antes de crear el stash actualiza el Staging Index con `git add -u` si ya tienes archivos en el Staging Index para asegurarte de que realmente vas a guardar todos los cambios que has hecho en esos archivos.** Sino se guardarán en el estado que tenían cuando los añadiste al Staging Index y perderás parte de tu trabajo actual.

- **Después de hacer un stash** tu **Working Directory** está **_CLEAR_** y puedes moverte entre todas las ramas disponibles sin problemas de perder tus últimos cambios no comiteados.
  
  **Pero si tienes archivos nuevos sin seguimiento (`untracked`) los seguirás viendo en tu Working Directory después de crear el stash.**
  
  Lo mismo ocurrirá si usas el flag `--keep-index`.
  
  **Si quieres evitarlo, crea el stash con el flag `--include-untracked`.**

- Una vez creado un stash puedes hacer cambios, crear nuevos commits, moverte a otra rama y/o ejecutar cualquier otra operación de Git. Luego **podrás recuperar tu trabajo en cualquier momento y en cualquier rama**.

- Si cuando recuperas el trabajo de un stash con `git stash apply` o `git stash pop` surgen conflictos durante el auto-merge, es necesario solucionarlos manualmente (los archivos tienen estado `UU`) y confirmarlos con `git add` para cada archivo y `git commit -m`, o bien con `git commit -am`.

  Además, cuando usas `git stash pop`, si surge un conflicto el stash no se elimina de la lista y es necesario eliminarlo manualmente con `git stash drop stash@{<num>}`.
  
  Cuando usas `git stash apply` el stash nunca se elimina de la lista, aunque no hayan surgido conflictos. Así puedes usar el mismo stash en otras ramas, por ejemplo.

- **Por defecto un stash guarda los archivos que están en seguimiento (*TRACKED*)**, que son aquellos que has añadido al Staging Index y los que no están ahí pero que Git ya los está siguiendo porque se incluyeron en el último commit y entonces también reconoce si han sido modificados.

  - **Si también quieres guardar los archivos UNTRACKED** (archivos nuevos que hayas generado y que no hayas añadido al Staging Index) tienes que usar el flag `-u | --include-untracked`.
  
  - **Si también quieres guardar los archivos UNTRACKED y además los IGNORED** tienes que usar el flag `-a | --all`.

   <a name="stash-flags-warning"></a> 
  - **IMPORTANTE: si usas la opción `-u` o `-a`, al recuperar un stash con `apply` o `pop` Git insistirá en volcar en el Working Directory el contenido del commit generado para los archivos untracked y/o ignorados. Y el volcado solo funcionará si esos mismos archivos no existen o bien tienen exactamente el mismo contenido.**
  
    Para asegurarte de que se va a poder hacer este volvado, tienes 3 opciones:

    1. Ejecutar antes `git clean`. IMPORTANTE: asegúrate primero de que esos archivos pueden ser eliminados, porque recuerda que los `untracked files` (`ignored` o no) no existen en ninguna otra parte del repositorio Git y no se podrán recuperar después.

    2. Copiar antes los `untracked files` (`ignored` o no) en otro directorio para tener una copia de seguridad.

    3. Hacer antes un `git stash save -u` o `git stash save -a`, ya que estos comandos harán internamente un `git clean` por ti. Pero esta opción te deja con otro stash del mismo tipo que estás intentando solucionar que tendrás que tratar más tarde del mismo modo.

- Dependiendo de la opción que utilices Git hará entre 2 y 3 commits para almacenar la información del stash. Por eso si haces `git log` ves una rama adicional con varios commits. ([Ver Sección: How git stash works](https://es.atlassian.com/git/tutorials/saving-changes/git-stash#stashing-your-work)):

  - **`git stash    = 2 commits`**
    
    El primero para `changes staged in the index` y el segundo para `unstaged changes`.
  
  - **`git stash -k = 3 commits`**
    
    Los dos anteriores y otro para los `changes to untracked files`.

  - **`git stash -a = 3 commits`**
    
    Los tres anteriores, pero el tercero incluye además los `ignored files`.

- **Los stashes son locales a tu repositorio. No se suben al repositorio remoto cuando haces un `git push`**.

- Ejemplo del listado que muestra `git stash list`:

  ```php
  stash@{0}: "WIP on ... | mensaje del stash (si se definió alguno)" // ---> NEWEST
  stash@{1}: "WIP on ... | mensaje del stash (si se definió alguno)"
  stash@{2}: "WIP on ... | mensaje del stash (si se definió alguno)"
  stash@{3}: "WIP on ... | mensaje del stash (si se definió alguno)" // ---> OLDEST
  ```

- **IMPORTANTE** sobre `git stash list`:

  - **El *stash* más reciente siempre es el `stash@{0}`**, porque la lista se comporta como una pila **LIFO** (*Last In - First Out*).

  - **Buena práctica:** generar los ***stash* con mensaje** con "`git stash save "<message>"`" para aclarar en qué punto te habías quedado. De este modo te será mucho más fácil distinguirlos.

  - `git stash apply` y `git stash pop` por defecto siempre recuperan el stash más reciente: `stash@{0}`.

  - **Siempre mejor usar** `git stash apply` en lugar de `git stash pop`, porque así podrás revisar los cambios que se van a incorporar y siempre estarás a tiempo de descartar la operación y volcar el stash en otra rama de forma segura con `git stash branch <nombre-rama> stash@{<num-stash>}`. **IMPORTANTE:** en el caso haber creado el stash con la opción `-u` o `-a`, [LEER ESTE AVISO DE ARRIBA](#stash-flags-warning).

- Si has recuperado un stash en el momento equivocado, **puedes deshacer el `git apply` justo después de haberlo ejecutado si todavía no has hecho ningún nuevo cambio**:
  
  Así evitas tener que volver a crear un stash (que sería idéntico al que ya tienes en la lista) para continuar.

  ```php
  git stash show -p | git apply --reverse  // Deshace la restauración de un `git apply` recién ejecutado, siempre y cuando no hayas hecho ningún nuevo cambio después de ejecutar el `git apply`.
  // - or -
  git stash show -p | git apply -R
  ```

- **Si quieres evitar tener que resolver los conflictos de merge que puedan surgir cuando recuperes el stash, puedes recuperar el stash en una nueva rama que haga el *fork* en el commit donde lo creaste.**

  Es muy útil cuando la rama donde ejecutaste el `git stash save` se ha ido actualizando desde que creaste el stash. Al restaurar el stash por encima del commit original no se producen conflictos.

  ```php
  git stash branch <branch-name> [stash@{<num>}]  // Crea una nueva rama a partir del commit desde el que se generó el stash para preservar el estado original del que partía; luego hace un checkout para ubicarse en ella y ejecuta un "git stash pop" del último stash ("stash@{0}", u otro si indicas su referencia) para volcar su contenido. 
  ```

```php
git stash                                       // Guarda todos los archivos del Working Directory y del Staging Index. Excluye archivos nuevos `untracked` (permanecerán en el Working Directory).
git stash save                                  // Guarda todos los archivos del Working Directory y del Staging Index. Excluye archivos nuevos `untracked` (permanecerán en el Working Directory).
git stash save "<message>"                      // Guarda todos los archivos del Working Directory y del Staging Index con un mensaje. Excluye archivos nuevos `untracked` (permanecerán en el Working Directory).
git stash save -k | --keep-index                // Guarda todos los archivos del Working Directory pero no los que están en el Staging Index. Excluye archivos nuevos `untracked` (permanecerán en el Working Directory). Es decir, solo guarda los archivos del Working Directory que están en seguimiento debido a que ya existían en el commit anterior. Este flag es muy práctico si estás editando varios archivos y quieres guardar varios para editarlos más tarde pero seguir trabajando con los demás. Los que quieres seguir editando los dejas en el Staging Index y haces el `git stash`. Así ya puedes continuar viendo únicamente los archivos que tienes en el Staging Index.
git stash save -u | --include-untracked         // Guarda todos los archivos del Working Directory y del Staging Index, incluyendo archivos nuevos `untracked` del Working Directory.
git stash save -a | --all                       // Guarda todos los archivos del Working Directory y del Staging Index, incluyendo archivos nuevos `untracked` del Working Directory y archivos ignorados por el archivo ".gitignore" de Git.

// IMPORTANTE: si usas `git stash save -u` o `git stash save -a`, al recuperar un stash con `apply` o `pop` Git insistirá en volcar en el Working Directory el contenido del commit generado para los archivos untracked y/o ignorados. Y el volcado solo funcionará si esos mismos archivos no existen o bien tienen exactamente el mismo contenido.

git stash list                                  // Lista con todos los stash guardados.
git stash list --stat                           // Lista con todos los stash guardados con los cambios de cada stash.
git stash apply                                 // Restaura el stash más reciente (siempre es el "stash@{0}") sin eliminar su registro de la lista de stashes.
git stash apply --index                         // Restaura el stash más reciente (siempre es el "stash@{0}") sin eliminar su registro de la lista de stashes y recupera la información de los archivos que estaban en el Staging Index cuando creaste el stash.
git stash apply --index stash@{<num>}           // Restaura el stash indicado sin eliminar su registro de la lista de stashes y recupera la información de los archivos que estaban en el Staging Index cuando creaste el stash.
git stash apply stash@{<num>}                   // Restaura el stash indicado sin eliminar su registro de la lista de stashes.
git stash show -p | git apply --reverse         // Deshace la restauración de un `git apply` recién ejecutado, siempre y cuando no hayas hecho ningún nuevo cambio después de ejecutar el `git apply`. Muy útil cuando has restaurado un stash por error cuando todavía no era el momento adecuado. Así evitas tener que volver a crear un stash (que sería idéntico al que ya tienes en la lista) para continuar. (Fuentes: https://stackoverflow.com/a/1021867, https://stackoverflow.com/a/29815408).
git stash pop                                   // Restaura el stash más reciente (siempre es el "stash@{0}") y elimina su registro de la lista de stashes. Es equivalente a: "git stash apply" + "git stash drop".
git stash pop stash@{<num>}                     // Restaura el stash indicado y elimina su registro de la lista de stashes. Es equivalente a: "git stash apply" + "git stash drop".
git stash drop                                  // Elimina el stash más reciente (siempre es el "stash@{0}") de la lista de stashes.
git stash drop stash@{<num>}                    // Elimina el stash indicado de la lista de stashes.
git stash clear                                 // Elimina todos los registros de la lista de stashes sin preguntar y ya no se pueden recuperar.
git stash branch <branch-name> [stash@{<num>}]  // Crea una nueva rama a partir del commit desde el que se generó el stash para preservar el estado original del que partía; luego hace un checkout para ubicarse en ella y ejecuta un "git stash pop" del último stash ("stash@{0}", u otro si indicas su referencia) para volcar su contenido. Es muy útil cuando la rama donde ejecutaste el "git stash save" se ha ido actualizando desde que creaste el stash y quieres evitar tener que resolver los conflictos de merge que puedan surgir cuando recuperes su contenido. Al restaurar el stash por encima del commit original no se producen conflictos.
git stash show                                  // Muestra los cambios del último stash
git stash show -p                               // Muestra los cambios del último stash con más información
git show stash                                  // Muestra los cambios del último stash con más información todavía (Commit SHA-1, Author, Date, Commit message)
git show stash@{<num>}                          // Muestra los cambios del stash indicado con más información todavía (Commit SHA-1, Author, Date, Commit message)
```

(Fuente: https://git-scm.com/docs/git-stash)


# Clean <a name="clean"></a>

El comando `git clean`:

- Actúa sobre los archivos sin seguimiento (*untracked*), justo lo contrario que `git checkout` y `git reset`.

- **Elimina los archivos del Working Directory que no están en seguimiento.**

- Por seguridad y por defecto no elimina nada porque sus cambios no se pueden deshacer. Es necesario indicarle la opción `-f` de forzar borrado.

- Por seguridad y por defecto no actúa recursivamente sobre los directorios. Es decir, si haces `git clean -n` solo ves nombres de archivos, pero no directorios. Con `git clean -dn` entonces sí los ves.

- Opciones:

    - **`-n`:** es un *"dry run"* del `git clean`. Es decir, muestra los archivos que se eliminarían si se ejecutara `git clean -f`, pero no los elimina. **Es recomendable empezar por este comando**

    - **`-f` | `--force`:** inicia la eliminación de los archivos sin seguimiento.

       - No elimina directorios sin seguimiento ni los archivos ignorados por el archivo `.gitignore`.

       - Es necesario usar esta opción `-f` para llegar a eliminar el contenido deseado, a no ser que la opción de configuración `clean.requireForce` esté seteada como `false` (no recomendado).

    - **`-d`:** incluir los directorios sin seguimiento. Se puede aplicar a las opciones anteriores:

       - **`-dn`:** ver archivos y directorios sin seguimiento que se eliminarían.

       - **`-df`:** eliminar archivos y directorios sin seguimiento.
       
    - **`-x`:** incluir los archivos ignorados por `.gitignore`. Se puede aplicar a las opciones anteriores:

       - **`-xn`:** ver archivos sin seguimiento y archivos ignorados que se eliminarían.

       - **`-xf`:** eliminar archivos sin seguimiento y archivos ignorados.

    - **`-dxn`:** ver archivos y directorios sin seguimiento, y archivos ignorados que se eliminarían.

    - **`-dxf`:** eliminar archivos y directorios sin seguimiento, y archivos ignorados.

    - **`-i`:** modo interactivo. Muestra las opciones disponibles para actuar durante el proceso de eliminación. En cada paso te pregunta con `What now>` e introduces uno de los siguientes valores:

       ```
       1: cleanstart cleaning

       2: filter by pattern - exclude items from deletion (puedes escribir *.txt, por ejemplo, para que **excluya** esos archivos)

       3: select by numbers - select items to be deleted by numbers select by numbers

       4: ask each - confirm each deletion (like "rm -i")

       5: quit - stop cleaning

       6: help - this screen
      ```


# Prune <a name="prune"></a>

*PENDIENTE ANALIZARLO*

```php
git prune          //
git fetch --prune  // = git fetch --all && git remote prune
git remote prune   //                              
```

(Fuente: https://es.atlassian.com/git/tutorials/git-prune)


# Trabajo con repositorios remotos <a name="trabajo-con-repositorios-remotos"></a>


## Clone <a name="clone"></a>

`git clone <URL-HTTPS-or-SSH> [<dir-name>]` hace un fetch del código de un repositorio remoto para que puedas crear una copia local. Si se especifica un `<dir-name>` no se usará el nombre propio del repositorio clonado.


## Remote <a name="remote"></a>

El comando `git remote` te permite:

- Administrar los repositorios remotos para que te conectes a ellos bajo un nombre más manejable en lugar de tener que escribir toda la URL cada vez.

- Ver los repositorios remotos que tienes, editarlos y/o eliminarlos.

- Para conectar un repositorio local con un repositorio remoto se debe configurar Git para que apunte a él mediante el comando `git remote add <name> <URL>`.

  **Que el repositorio sea remoto no implica que deba estar en la red o en Internet. Puede estar en otro directorio de tu *host* local perfectamente. Porque en Git, "remoto" significa que se encuentra en un lugar distinto al repositorio en el que estás. De modo que los comandos para comunicarse con un repositorio remoto, sea cual sea su ubicación, son exactamente los mismos y hacen las mismas funciones.**

  > **Ejemplo de trabajo con repositorio remoto local:** configuras un repositorio para desarrollo en el directorio del proyecto y, adicionalmente, creas un repositorio remoto para "producción" que esté en `C:\xampp\htdocs\<dir-name>` (es remoto porque está en un directorio distinto). Al repositorio de producción solo le envías la rama master actualizada para ver el proyecto en el navegador como si ya estuviera online.

- Muestra el nombre del/los repositorio/s remoto/s que tengamos asociado/s al repositorio local.

  > Los repositorios remotos que añades a tu repositorio local solo son visibles desde ese repositorio en particular. Es decir, los repositorios remotos no se añaden a Git como si fueran a parar a un archivo global a modo de agenda, donde pudieras consultar todos los repositorios remotos con los que ya has trabajado para disponer de ellos desde cualquier repositorio local.

- Si es un repositorio local creado desde cero, el comando `git remote` no mostrará nada porque no está conectado a un repositorio remoto. En este caso hay que conectarlo manualmente con `git remote add <name> <URL>`.

- Por defecto, al hacer un `git clone` se genera un remoto que se llama **"origin"**.

- Si colaboramos en un repositorio público en el que no tenemos permisos de escritura para hacer `git push`, normalmente crearemos primero un *fork* del repositorio original en nuestra cuenta personal de GitHub y luego haremos un `git clone` de nuestro *fork* para trabajar en local. En este punto tendremos que **configurar el repositorio local con dos servidores remotos**:

    - El primero, **origin**, para subir nuestros cambios al repositorio remoto de nuestra cuenta personal (*fork*) para luego poder hacer los Pull Requests que queramos al repositorio remoto original.

    - Y el segundo, **upstream**, apuntando al repositorio remoto original para poder obtener los últimos cambios que vayan surgiendo cada vez que un Pull Request de otro colaborador sea incorporado a la rama master. Aunque no tengamos permisos de escritura para hacer `git push upstream` sobre este repositorio, sí que nos deja hacer `git fetch upstream` para actualizar nuestro repositorio local.

    Así nos aseguramos de poder actualizar nuestro *fork* y copia local:

    ```php
    git remote add upstream <repo-original>
    git fetch upstream
    git log --oneline master..origin/master
    git checkout master
    git log upstream/master
    ```

    Si nos parece bien, ya podemos hacer el merge para incorporar todos los cambios en el repositorio local:

    ```php
    git merge upstream/master
    ```

    Quedaría pendiente:

     - Si tenemos una rama de desarrollo personal derivada de master, por ejemplo, actualizarla haciendo un merge o rebase de la rama master en nuestra rama personal.
     
     - Incorporar todos los cambios en el repositorio remoto del *fork* (**origin**).

- Aunque en los ejemplos que se suelen ver en las documentaciones de Git solo existe el repositorio remoto "origin" y como mucho también el de "upstream", es perfectamente válido y común añadir tantos remotos como se necesiten. Sería el caso si estuvieras trabajando en un mismo proyecto con varios colaboradores, por ejemplo. Así podrías obtener contribuciones de cada uno con `git pull` fácilmente.

- **MUY IMPORTANTE: cuando accedes a una rama remota que está en seguimiento, como por ejemplo `origin/master`, Git te muestra el estado que tenía la última vez que accediste a ella.** Es decir, **no debes considerarla como si fuera el estado real del repositorio remoto**, porque si no la has actualizado en tu repositorio local recientemente no coincidirá con su estado actual del repositorio remoto.

```php
// INFORMACIÓN
git remote                                             // Muestra el nombre del/los repositorio/s remoto/s que tengamos asociado/s al repositorio local. Si es un repositorio local creado desde cero no mostrará nada porque todavía no está conectado a un repositorio remoto. En este caso hay que conectarlo manualmente con "git remote add <name> <URL>". Por defecto en cada CLONE se le llama "origin".
git remote -v                                          // Muestra las URLs que Git usa para hacer FETCH y PUSH a cada repositorio remoto que tengas configurado.

git remote show <remote>                               // Muestra más información sobre el repositorio remoto <remote> especificado.
git remote show origin                                 // Muestra más información sobre el repositorio remoto "origin". Muestra la rama a la que automáticamente se suben los cambios cuando ejecutas `git push` estando en ciertas ramas. También muestra qué ramas remotas del servidor todavía no tienes, qué ramas remotas tienes que han sido eliminadas del servidor, y múltiples ramas locales que son capaces de ser mergeadas automáticamente con sus respectivas ramas remotas cuando ejecutas `git pull`.
git ls-remote <remote>                                 // Muestra una lista con todas las referencias remotas del <remote>.

// AÑADIR
git remote add <name> <URL-HTTPS-or-SSH>               // Añade el repositorio remoto <URL> para poder conectarse a él desde el repositorio local usando el nombre <name>.
git remote add origin <URL-HTTPS-or-SSH>               // Añade el repositorio remoto <URL> para poder conectarse a él desde el repositorio local usando el nombre "origin" (convención). Si colaboramos en un repositorio público en el que no tenemos permisos de escritura para hacer `git push`, "origin" será el repositorio remoto de nuestra cuenta personal de GitHub desde el que podremos hacer los Pull Requests.
git remote add upstream <URL-HTTPS-or-SSH>             // Añade el repositorio remoto <URL> para poder conectarse a él desde el repositorio local usando el nombre "upstream" (convención). Si colaboramos en un repositorio público en el que no tenemos permisos de escritura para hacer `git push`, "upstream" será el repositorio remoto original para obtener los últimos cambios que vayan surgiendo cada vez que un Pull Request de otro colaborador sea incorporado a la rama master.

// ELIMINAR
git remote prune origin --dry-run                      // Muestra todas las ramas que se eliminarán si se ejecuta "git remote prune origin", pero no las elimina.
git remote prune origin                                // Elimina del repositorio local todas las ramas remotas que han sido eliminadas previamente del repositorio remoto y que todavía están disponibles en local (ramas obsoletas, o "stale branches"); pero que no es posible eliminarlas con "git push origin :<branch>" porque ya se ha perdido su referencia. Es necesario ejecutarlo para limpiar el repositorio local cuando desde GitHub se ha aceptado un Pull Request (PR) y se ha eliminado la rama (solamente del servidor remoto) después de hacer el merge del PR.
git remote remove <remote>                             // Elimina la referencia <remote> de un repositorio remoto. Posibles motivos: has movido el servidor; ya no estás usando un "mirror" en concreto; o un colaborador ya no está colaborando más. También elimina todas las ramas remotas que están en seguimiento, así como los ajustes de configuración asociados con ese <remote>.
git remote rm <remote>                                 // Igual que el anterior.

// EDITAR
git remote rename <old-remote-name> <new-remote-name>  // Renombra el "shortname" del repositorio remoto. También cambia el nombre de todas tus ramas remotas que están en seguimiento. Es decir, si antes estaban referenciadas como "pb/master", por ejemplo, ahora se llamarían "paul/master".
git remote set-url <nombre-repositorio> <nueva-URL>    // Muy útil y necesario cuando haces un CLONE del repositorio original y luego creas en tu cuenta de GitHub un repositorio vacío donde quieres subir todo el repositorio local. En este punto tienes que actualizar las URLs FETCH y PUSH del repositorio remoto "origin" (configurado por defecto por el CLONE) al que apunta Git para que puedas hacer PUSH de tus cambios en tu cuenta personal en lugar de al repositorio original, ya que normalmente en el original no tendrás permisos de escritura.
```


## Fetch <a name="fetch"></a>

El comando `git fetch` se comunica con el repositorio remoto para obtener toda la información de todas las ramas (commits y archivos) que no posee el repositorio local y la guarda en la base de datos local, pero no modifica el Working Directory.

Después de hacer `git fetch <remote>` deberías tener referencias de todas las ramas para poder hacer merge y/o inspeccionarlas en cualquier momento.

```php
git fetch <remote>           // Obtiene del repositorio remoto <remote> toda la información de todas las ramas que le falta al repositorio local.
git fetch upstream           // Obtiene del repositorio remoto "upstream" toda la información de todas las ramas que le falta al repositorio local.
git fetch <remote> <branch>  // Obtiene del repositorio remoto <remote> toda la información de la rama <branch> que le falta al repositorio local.
git fetch --all              // Obtiene de todos los repositorios remotos toda la información de todas sus ramas que le falta al repositorio local.
git fetch --dry-run          // Muestra ejemplos de las acciones que haría durante el fetch, pero no las aplica.
```


### Cómo actualizar la rama master local con todos los cambios que han surgido en el repositorio remoto <a name="como-actualizar-la-rama-master-local-con-todos-los-cambios-que-han-surgido-en-el-repositorio-remoto"></a>

```php
git fetch origin
git log --oneline master..origin/master

git checkout master
git log origin/master

// Si nos parece bien, ya podemos hacer el merge para incorporar todos los cambios:

git merge origin/master

/*
Quedaría pendiente:
  - Si tenemos una rama de desarrollo personal derivada de master, por ejemplo, actualizarla haciendo un merge o rebase de la rama master en nuestra rama personal.
  - Incorporar todos los cambios en el repositorio remoto del *fork* (**origin**).
*/
```


### Tracking branches <a name="tracking-branches"></a>

Al hacer `git checkout -b <new-branch> <remote-branch>` de una rama remota de seguimiento automáticamente Git crea una **"tracking-branch"** local (rama de seguimiento). La rama remota a la que sigue se llama **"upstream branch"**.

Una **tracking-branch** es una rama local que tiene una relación directa con una rama remota (**upstream-branch**).

Si estás en una **tracking-branch** y haces `git pull`, automáticamente Git sabe de qué servidor tiene que obtener la información y en qué rama tiene que hacer el merge.

Estando en una **tracking-branch** puedes referirte a su **upstream branch** con el shorthand `@{upstream}` o `@{u}`. Ejemplo: si estás en la rama master puedes hacer `git merge @{u}` en lugar de `git merge origin/master`.

Cuando clonas un repositorio, Git generalmente crea automáticamente una rama master que hace seguimiento de origin/master. Sin embargo, puedes configurar otras **tracking branches** si lo deseas; unas que sigan ramas de otros remotos, o no seguir la rama master.

El comando `git clone` configura automáticamente tu rama master local para que siga la rama master remota (o como se llame la rama por defecto) del servidor del que has clonado el repositorio. Al ejecutar `git pull` normalmente obtiene la información del servidor del que tú clonaste originalmente el repositorio, y automáticamente intenta hacer un merge en el código en el que actualmente estás trabajando.


### Cómo ver las tracking branches que están configuradas <a name="como-ver-las-tracking-branches-que-estan-configuradas"></a>

```php
git branch -vv  // Muestra todas las ramas y si tienen configurada alguna "upstream branch", cuántos commits por delante y por detrás están respecto a ellas (si no sale esta información significa "up-to-date"), y el SHA-1 y el mensaje del último commit.
```

**MUY IMPORTANTE:** las cantidades de commits por delante y por detrás que está cada rama local (*tracking-branch*) respecto a su **upstream branch** se obtienen tomando como referencia el estado de la última vez que hiciste **fetch** de cada **upstream branch**. Este comando no muestra las cantidades con respecto al estado actual de las **upstream branches** remotas, sino sobre lo que tiene en la caché local sobre las remotas.

Si quieres saber las cantidades con respecto al estado actual de las **upstream branches** remotas, primero tienes que hacer un fetch de todas las ramas remotas y luego ejecutar el comando anterior. Se pueden ejecutar los dos comandos a la vez de la siguiente manera:

```php
git fetch --all; git branch -vv  //
```


#### Cómo crear una *tracking-branch* en el repositorio local <a name="como-crear-una-*tracking-branch*-en-el-repositorio-local"></a>

**Cómo trabajar en una rama remota obtenida con `git fetch`:**

Cuando al hacer un `git fetch origin` obtienes la referencia de una nueva rama de seguimiento (*tracking-branch*), Git solo te genera un puntero a "origin/remote-branch" que no puedes modificar.

Es decir, no te genera automáticamente una copia local editable de esa rama también, por lo que no puedes empezar a trabajar en ella directamente.

Si quieres poder trabajar en ella debes hacer un `git merge origin/remote-branch` en tu rama de trabajo actual. Y/o si quieres tu propia rama que empiece donde termina la remota, puedes crearte una basándote en esa con `git checkout -b <new-branch> <remote-branch>`.

Desde este momento tu rama estará siguiendo a la rama remota (Git muestra un mensaje como éste: "Branch `<new-branch>` set up to track remote branch `<remote-branch>` from `<remote>`.").

```php
git checkout -b <new-branch> <remote-branch>   // Es la opción más larga de escribir, pero la única que te permite asignarle un nombre distinto al de la rama remota.
// - or -
git checkout --track <remote>/<remote-branch>  // Es un shortcut del comando anterior, pero no te permite elegir el nombre de tu tracking-branch local.
// - or -
git checkout <remote-branch>                   // Es el shorcut del shortcut anterior. Funciona solo si (1) no existe ese nombre de rama y (2) si el nombre coincide solo con el nombre de una rama que exista en solo un remote.

// En ambos casos obtienes el siguiente mensaje:

Branch serverfix set up to track remote branch serverfix from origin.
Switched to a new branch 'serverfix'

// También puedes decidir en cualquier momento que una rama tenga como "upstream branch" a una rama remota en concreto:
git branch -u <remote>/<remote-branch>         // Setea la "upstream branch" de la rama actual o, si ya tenía una, la modifica.
Branch serverfix set up to track remote branch serverfix from origin.
```


## Pull <a name="pull"></a>

El comando `git pull` es una combinación de `git fetch` y `git merge`:

- Se comunica únicamente con el repositorio y la rama remota a la que tu rama actual está haciendo el seguimiento. Obtiene toda la información (commits y archivos) que no posee tu rama actual del repositorio local y la guarda en la base de datos local.
- Seguidamente intenta hacer un merge en la rama actual en la que te encuentras con los cambios que te faltan de la rama remota.

```php
git pull                    // "git fetch" + "git merge"
git pull --rebase           // Fuerza a Git para que integre los cambios de la rama remota efectuando un "rebase" en lugar de un "merge", que es la opción por defecto de "git pull". Útil para intenta solucionar los problemas ocasionados al hacer "git pull" cuando alguien ha hecho lo que no se debe hacer nunca: un rebase de commits que ya se habían hecho públicos y en los que nos hemos podido estar basando para crear nuestro trabajo; y ese alguien los ha subido con "git push --force" para forzar reescribir la historia del repositorio remoto.
git pull --all              // Hace un "git fetch" de todas las referencias de todos los repositorios remotos configurados en lugar de solo el necesario. Es útil cuando con "git pull" no consigues obtener una nueva rama remota.
git pull <remote> <branch>  // Obtiene la información del repositorio <remote> y la rama <branch> indicada. Incorpora al repositorio local los últimos cambios del repositorio remoto para que luego puedas hacer un PUSH al repositorio remoto (origin) para tenerlo actualizado. MUY IMPORTANTE: ejecutarlo cada vez que un Pull Request sea aceptado en el "upstream".
git pull upstream master    // 
```


## Push <a name="push"></a>

El comando `git push` se comunica con el repositorio remoto para subir todos los cambios generados en el repositorio local que no se encuentran en el remoto.
Es un comando que requiere permisos de escritura: debes introducir tu usuario y contraseña para poder acceder al repositorio remoto.

> Con el comando `git config --global credential.helper cache` puedes almacenar temporalmente tus credenciales en la caché de Git durante unos minutos para no tener que introducir tu usuario y contraseña cada vez que quieras hacer un `git push`.

Solo puedes hacer PUSH si has clonado un repositorio al que tienes permiso de escritura y si otro colaborador no lo ha hecho antes que tú desde entonces.

Es decir, si tú y otra persona clonáis el repositorio a la vez, y la otra persona hace un `git push upstream` y luego tú también, tu push será rechazado porque le faltará parte de la historia. Primero tendrás que hacer un `git fetch upstream` para obtener los cambios incorporados por esa persona y, una vez hayas actualizado tu repositorio, te permitirá hacer el `git push upstream`.

```php
// HISTORIAL DE COMMITS
git push                                         // Solo funciona si primero has hecho un push con la opción `-u` (git push -u <remote> <branch>).
git push <remote> <branch>                       // Sube todos los cambios generados en la rama <branch> del repositorio local que no se encuentran en la rama remota. Si es la primera vez que ejecutas este comando entonces crea la rama <branch> en el <remote>.
git push origin master                           // 
git push <remote> <branch>:<remote-branch-name>  // Igual que el anterior, pero te permite subir la rama local al repositorio remoto con un nombre distinto.
git push <remote> <branch> --force               // Fuerza a subir todos los cambios generados en la rama <branch> del repositorio local a la rama remota. Ejemplo de caso de uso: cuando ya has subido tus cambios al repositorio remoto y te das cuenta que necesitas hacer un "--amend" del mensaje del commit. Después de hacer el "--amend" necesitas ejecutar este comando para que también se vea reflejado en el repositorio remoto.
git push -u <remote> <branch>                    // La opción "-u" permite que la próxima vez que hagas un PUSH no tengas que indicar de nuevo ni el repositorio ni la rama de destino.
git push -u origin master                        // 

// TAGS
git push --tags                                  // Sube todos los tags al repositorio remoto. IMPRESCINDIBLE después de subir un repositorio a GitHub, porque los tags no se suben automáticamente; hay que hacerlo manualmente. NO ES RECOMENDABLE SUBIRLOS SIEMPRE TODOS. Es mejor usar "git push <remote> <tag>" para evitar subir tags antiguos malos.
git push <remote> <tag>                          // Sube al repositorio remoto solo el tag especificado. Es la OPCIÓN RECOMENDADA. Después de haberlos subidos todos por primera  vez luego es mejor usar "git push <remote> <tag>" para evitar subir tags antiguos malos.
git push origin <tag>                            //

// ELIMINAR RAMA
// Todas estas opciones lo que hacen es eliminar el puntero del servidor. Pero Git normalmente guardará la información eliminada por un tiempo hasta que el Garbage Collector haga la limpieza. De manera que si una rama remota ha sido eliminada accidentalmente, normalmente es fácil de recuperar.

git push <remote> --delete <branch>              // Elimina la rama <branch> del repositorio remoto <remote>.
// - or -
git push <remote> :<branch>                      // Elimina la rama <branch> del repositorio remoto <remote>.
git push origin :<branch>                        // Elimina la rama <branch> del repositorio remoto origin.
```


# GitHub <a name="github"></a>


## Pull Request <a name="pull-request"></a>

**Cuando envías un Pull Request y todavía no ha sido aprobado, si *a posteriori* haces una modificación que pertenece a la rama enviada, no es necesario que vuelvas a hacer el Pull Request.** Con hacer el `git push` para actualizar el contenido en el repositorio remoto "origin" es suficiente, porque GitHub actualiza automáticamente los commits del *newsfeed* del Pull Request existente.


### Opciones de merge <a name="opciones-de-merge"></a>

- **Merge pull request:**
  Hace un merge normal. Todos los commits de la "feature branch" se conservan por completo y se unen a la rama base con un nuevo commit. Las dos ramas quedan vinculadas por este nuevo commit.
      
- **Squash and merge:**
  Combina todos los commits de la "feature branch" en uno solo, y este commit lo añade al final de la rama base, pero sin vincularlo con la "feature branch". La "feature branch" se conserva por completo.

- **Rebase and merge:**
  Traslada todos los commits de la "feature branch" a la punta de la rama base, pero creando un nuevo SHA-1 para cada uno de esos commits (y, como es GitHub, también actualiza la información del commiter, cosa que no ocurre con el comando de Git `git rebase`). La "feature branch" desaparece por completo.

(Fuente: https://help.github.com/en/articles/about-pull-request-merges)

(Fuente: https://stackoverflow.com/a/43551395) (mucho más claro)


## Uso de referencias en comentarios <a name="uso-de-referencias-en-comentarios"></a>

Podemos crear un enlace a un commit, issue, comentario o a cualquier otra referencia dentro de cualquier caja de comentario de GitHub.
Adicionalmente las referencias se pueden preceder por una de las siguientes tres palabras clave. Así queda más claro lo que se ha hecho en relación a esa referencia:

```php
"[...] fixes #<num> | <sha-1> [...]"
"[...] closes #<num> | <sha-1> [...]"
"[...] resolves #<num> | <sha-1> [...]"
```


# EXTRAS <a name="extras"></a>


## Conversores online Markdown &rarr; HTML <a name="conversor-online-markdown-html"></a>

- [Dillinger.io](https://dillinger.io/)

- [Stackedit.io](https://stackedit.io/)


## Uso de la consola <a name="uso-de-la-consola"></a>


### Cómo proceder cuando un comando de Git nos muestra dos puntos `:` para realizar una acción <a name="como-proceder-cuando-un-comando-de-git-nos-muestra-dos-puntos"></a>

Esto sucede cuando, por ejemplo, ejecutamos el comando `git rebase -i` y abre el editor Vim.

```php
// Los dos puntos ":" ya aparecen en la consola. No los debes escribir.

// Activar edición
:a

// Terminar de editar el archivo guardando los cambios
ESC
:wq    // write quit
ENTER 

// Salir del editor sin guardar los cambios
ESC
:q     // quit
ENTER
```


### Cómo mostrar directorios <a name="como-mostrar-directorios"></a>

```php
ls      // Ver nombres de los directorios visibles
ls -a   // Ver nombres de los directorios visibles y ocultos
ls -l   // Ver nombres de los directorios visibles e información básica
ls -al  // Ver nombres de los directorios visibles y ocultos e información básica
```


### Cómo crear un archivo vacío <a name="como-crear-un-archivo-vacio"></a>

```php
touch <file-name>  // Crear archivo vacío
```


### Cómo escribir en un archivo (en Windows Bash) <a name="como-escribir-en-un-archivo-en-windows-bash"></a>


#### Escribir una sola línea <a name="escribir-una-sola-linea"></a>

```php
echo "Texto de una sola línea" > nombre.txt  //
```


#### Escribir múltiples líneas (opción 1) <a name="escribir-multiples-lineas-opcion-1"></a>

```php
(
echo Línea 1
echo Línea 2
echo Línea 3
echo           // Línea en blanco
echo           // Línea en blanco
echo           // Línea en blanco
echo           // Línea en blanco
echo Línea 4
echo Línea 5
echo Línea N
) > nombre.txt  //
```


#### Escribir múltiples líneas (opción 2) <a name="escribir-multiples-lineas-opcion-2"></a>

```php
echo "Línea 1" > nombre.txt
echo "Línea 2" >> nombre.txt
echo "Línea 3" >> nombre.txt
echo >> nombre.txt            // Línea en blanco
echo >> nombre.txt            // Línea en blanco
echo "Línea 4" >> nombre.txt
echo "Línea 5" >> nombre.txt
```

- El operador `>` crea el archivo si no existe y escribe en él. **Si el archivo ya existe reemplaza todo su contenido.**
- El operador `>>` crea el archivo si no existe y escribe en él. ** Si el archivo ya existe solo añade el nuevo contenido al final del mismo.**


### Cómo despejar la consola <a name="como-despejar-la-consola"></a>

`clear` despeja la consola ocultando los resultados anteriores en la parte superior, de modo que los puedes seguir consultando haciendo *scroll* hacia arriba.
