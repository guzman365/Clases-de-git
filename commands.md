# Commandos de git

* **`git --version`**

  Revisar la version de git de tu PC.

* **`git config --global user.name "Mau Reyes"`**

  Para poder configurar el nombre de usuario que esta trabajando con git

* **`git config --global user.email "reyes.marq@gmail.com"`**

  Permite configurar el email del usuario que esta trabajando con git.

* **`git config --global core.editor nano`**

  PErmite configurar el editor de texto de tu preferencia.  

* **`git config --list`**

  Consultar las configuraciones. ASi mismo se puede filtrar con grep de la siguiente manera. Si se quieren ver las configuraciones relacionadas al usuario `git config --list | grep user`

* **`git config <option>`**

  Permite verificar las opciones que se especifique en la ejecucion de comando. ej. `git config user.name` para poder verificar user_name

* **`git help <verb> ; git <verb> --help`**

  Permite ver la documentacion de algun comando, ej `git help config`