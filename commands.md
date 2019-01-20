# Commandos de git

* **`git --version`**

  Revisar la version de git de tu PC.

* **`git config --global user.name "Mau Reyes"`**

  Para poder configurar el nombre de usuario que esta trabajando con git

* **`git config --global user.email "reyes.marq@gmail.com"`**

  Permite configurar el email del usuario que esta trabajando con git.

* **`git config --global core.editor nano`**

  PErmite configurar el editor de texto de tu preferencia. (`git config --global core.editor "[your editor] -w"` this is to enforce git to wait your commit message on your editor)

* **`git config --list`**

  Consultar las configuraciones. ASi mismo se puede filtrar con grep de la siguiente manera. Si se quieren ver las configuraciones relacionadas al usuario `git config --list | grep user`

* **`git config --global alias.<cmd> <comando>`**

  Permite configurar un alias para cualquier comando. el `<cmd>` hace referencia al alias que quieras asignarle al `<comando>`.

* **`git config --global --unset <opcion>`**

  Permite remover configuraciones globales.

* **`git config <option>`**

  Permite verificar las opciones que se especifique en la ejecucion de comando. ej. `git config user.name` para poder verificar user_name

* **`git help <verb> ; git <verb> --help`**

  Permite ver la documentacion de algun comando, ej `git help config`

* **`git init`**

  Permite inicializar el repositorio de git, habiendo o no archivos.

* **`git status`**

  Muestra el estado del repositorio actualmente. Todos los archivos que no se estan siguiendo, Todos los archivos que estan en el area de preparacion.

* **`git add <file>`**

  Permite agregar archivos para poder seguir sus cambios. ej. `git add readme.md`. Si se quieren agregar todos los archivos en un solo comando es `git add .`. Asi mismo con el comando `git add -A` es para agregar todos los archivos y que ya estemos siguiendo con git. La diferencia entre el `.` y `-A`, es que el punto los agregara TODOS. y -A agregara unicamente los archivos que ya estemos siguiendo, pero no los nuevos.

* **`git commit -m "mensaje"`**

  Permite confirmar los cambios para registrar este cambio en la carpeta `.git`. ej `git commit -m "deployed chat"`.

* **`git commit`**

  Permite confirmar los cambios para registrar este cambio en la carpeta `.git`. Sin embargo, abre el editor que se configuro en core.editor

* **`git log`**

  Muestra el historial de confirmaciones o commits. Entre las opciones del comando podemos encontrar. `--oneline`: nos muestra el historial abreviado. `--graph`: añade un pequeño grafico ASCII mostrando el historial de ramificaciones y uniones. Se puede limiar el numero de commits que queremos ver `git log -2`. asi mismo la opcion `--reverse` muestra los git al reves. ASi mismo con `--pretty`. Si se quiere filtrar por fechas `git log --after="yyyy-mm-dd <time/>00>"`, `git log --before="yyyy-mm-dd <time/>00>"` ASi mismo se pueden utilizar ambas.

* **`git diff`**

  Muestra cual es la diferencia entre el ultimo estado de este archivo o de la zona de trabajo respecto a los archivos que ya estan confirmados o commiteados. Los archivos de la zona de trabajo vs, los archivos que tenemos en `.git`. Una variante seria `git diff --staged` por si hay el mismo archivo en el area de preparacion y en el area de trabajo.

* **`git reset HEAD <filename>`**

  Permite sacar un archivo del area de preparacion. ej `git reset HEAD readme.md` se esta sacando el archivo readme.md del area de preparacion, y se coloca nuevament en al area de preparacion.

* **`git commit --amend`**

  Para cambiar el mensaje del ultimo commit. Este comando lo que hace es abrir el editor que se configuro previamente en las configuraciones globales.

* **`git commit -a -m ""`**/**`git commit -am ""`**

  Permite saltarnos el area de preparacion. siempre y cuando los archivos ya se esten siguiendo.

* **`git rm`**

  Elimina archivos rastrados del repositorio y de nuestro directorio de trabajo de manera que no aparezcan la proxima vez como archivos no rastreados.

* **`git rm <file>`**

  Elimina archivos rastrados del repositorio y de nuestro directorio de trabajo de manera que no aparezcan la proxima vez como archivos no rastreados.

* **`git checkout -- <file>`**

  Te permite descartar los cambios en el directorio. Por ejemplo recuperar un archivo eliminado. 

* **`git mv <oldFile.ext> <newFile.ext>`**

  Te permite renombrar un archivo y agregarlo al area de preparacion para confirmar el cambio de nombre. Sino utilizamos este comando y renombramos el archivo desde otra fuente. Git reconocera que hemos eliminado un archivo(nombre anterior) y tenemos un nuevo archivo(nuevo nombre). Los dos cambios, el archivo eliminado y el archivo agregado tenemos que agregarlos al area de preparacion para confirmar los cambios. Entonces al utilizar este comando para renombrar el archivo nos ahorramos tres comandos. 
