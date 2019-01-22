# Clase 3

## Commit con el editor preconfigurado
Para poder lanzar el editor para poder redactar el mensaje de la cnofirmacion del commit simplemente se coloca git commit, sin pasarle el `-m` asi no mas.

Es recomendable que nuestra primer linea tenga 50 caracteres o menos que va a ser el titulo de nuestro commmit o de nuestro mensaje. Puedo agregar tantas lineas como quiera en el commit. Al momento de cerrar el archivo los cambios se guardan.

para poder utilizar siempre el comando `git commit -m ""` con saltos de linea se realizaria abriendo las primer par de comillas PERO NO LAS CIERRO hago el salto de linea y cuando he terminado con mi mensaje entonces cierro las comillas

Asi mismo el comando `git commit -a -m` permite saltarnos el area de preparacion para hacer el commit. Siempre y cuando los archivos ya se esten siguiendo, sino no me voy a poder saltar el area de preparacion. 

*Si se agrega un archivo nuevo y se hace una modificacion en cualquier otro archivo, y hacemos un `git status` nos daremos cuenta que tenemos, archivos modificados y untracked. Si nos saltamos el area de preparacion con `git commit -am` solo se agregaran los archivos al commit todos aquellos que esten siendo rastrados, pero no los untracked o nuevos files.*

## Eliminar archivos del repositorio
Para poder eliminar archivos rastrados del repositorio y de nuestro directorio de trabajo de manera que no aparezca la proxima vez como archivos no rastrados. 

Procedemos a eliminar el archivo manualmente desde el directorio 

Nos dira que el archivo ha sido elminado si le damos un `git status`. 

Ahora bien. podriamos utilizar cuaquiera de los siguiente comandos. 

`git add/rm <file>` para poder actualizar lo que se hizo en el siguiente commit.

`git checkout -- <file>` PAra descartar los cambios en el directorio. 

Algunas veces enviamos un archivo a la papelera y limpiamos la papelera de reciclaje. Perdiendo el archivo para siempre. Se puede utilizar un software que te busque todos esos archivos eliminados que los saque de la papelera de algun modo, porque necesito ese archivo. Pero lo unico que tengo que hacer para recuperar ese archivo es un checkout. 

*VENTAJA DE GIT ES QUE PODEMOS RECUPERAR ARCHIVOS FACILMENTE*

Si nosotros ya no queremos de verdad ya el archivo y elimnarlo, utilizamos el comando `git rm <file>`

Este archivo lo que hace es eliminarlo del historial de este punto en adelante y lo quita del directorio de trabajo tambien. Si es el unico archivo en la carpeta entonces tambien remueve la carpeta. 

Si se hace un git status, este cambio deleted aparecera en el area de preparacion para que se confirme, porque desde aqui en adelante ya no me interesa mantener este archivo en la historia.  

## Configuracion de alias comandos
Debido a que algunos comandos se utilizan regularlemtne, se puede configurar aliases para los comandos. 

Se pueden configurar a nivel de git o se pueden configurar a nivel del sistema operativo. 

Si se configuran por sistema operativo todo depende a que sistema operativo lo estas configurando. por ejemplo si se lanza el comando `gl` es equivalente a `git log --oneline`. Note, que no estoy haciendo referencia en ningun momento a git, en el comando.

Si se configura a nivel de git, entonces tendria que hacer referencia a git y al shortcut o alias de el comando que se configuro. Por ejemplo el siguiente comando `git st` hace referencia a `git status`. Esto se logra con el comando de configuracion global de la siguiente manera `git config --global alias.st status`. 

## Renombrar archivos
Git es lo suficientemente "inteligente" para entender cuando nosotros renombramos un archivo porque el analiza los cambios que tienen dentro, pero nosotros podemos decirle explicitamente a git que estamos renombrando un archivo con el archivo `git mv`. "git mv file_from file_to".

Mover el archivo teniendo incluso el mismo nombre a otra carpeta, es como si yo hubiese eliminado el archivo de la ubicacion inicial y hubiese creado un nuevo archivo en la nueva carpeta. Apesar de que el archivo tiene el mismo nombre, pero por tener otra ubicacion es un archivo totalmente diferente para el sistema de archivos, windows | linux | Mac. 

Con git pasa algo similar y sabe que se esta renombrando un archivo y nos dice en el historial que se ha renombrado. Con el comando `git mv oldFile.ext newFile.ext` git cambiara al nombre y lo agrega al area de preparacion, para que se proceda con el commit.

Ahora se puede hacer la pregunta, bueno porque no lo renombre y ya? Porque usar el comando `git mv`? Porque no le di click derecho y renombrar?. Porque si lo hacemos de esta manera sin utilizar el comando `git mv` git nos mostrara en un git status que hemos eliminado el archivo con el nombre anterior y que tenemos un nuevo archivo que no estamos siguiendo con el nombre nuevo.

Por ejemplo renombre un archivo preparar.md a git-add.md git nos mostrara lo siguiente.

```git
changes not staged for commit:
  deleted: preparar.md

untracked files:
  git-add.md
```

Entonces lo que nos esta ahorrando hacer el comando `git mv`. Nos esta ahorrando ir al editor darle click derecho y renombrar. Tener que hacer un `git rm viejoNombre` para poder eliminar el archivo con el nombre viejo. Agregar el nuevo archivo `git add nuevoNombre`. A este punto git, se dio cuenta que hicimos un renombramiento de archivos. 

```git
renamed: preparar.md -> git-add.md
```

git lo sabe porque el archivo tiene el mismo contenido, por eso es que se dio cuenta.

Significa que nos ahorramos el equivalente a tres comandos.

## Git log
Permite Mostrar los commits.

entre los cuales la opcion --oneline muestra los titulos. Esto es especialmente util porque solo nos interese conocer nada mas el checksum. Que es lo que se utiliza para regresar a ese commit. 

--graph: se puede utilizar juntas o independientes. Esto muestra las ramificaciones y una grafica de la rama master con las otras ramas. 

Es increible utilizar las dos juntas.

## git log --oneline --graph --pretty
A este comando se le pueden pasar muchas opciones. Para mas informacion buscar en `git log --help`.

`--pretty` es interesante porque podemos formatear como queremos que nos pase los mensajes de logs. por ejemplo el siguiente ejemplo

`git log --pretty=format:"%h - %an, %ar : %s"` mostrara el siguiente formato

```git
ef90255 - Mau Reyes, 53 minutes ago : Se creo el archivo git-mv.md
```

*En donde*

* `%h` es el checksum de confirmacion abreviada.
* `%an` el nombre del autor del commit.
* `%ar` Fecha de autoria relativa.
* `%s` titulo/asunto del commit.

Es especialmente util cuando estamos trabajando con un software externo que esta utilizando con nuestro historial. Muchas aplicaciones que nos permiten trabajar en equipo usan comandos como este precisamente para poder mostrarnos en tarjetitas las confirmaciones que se han hecho. 

## Filtrar commits que hay en un rango de fecha.
Si quiero saber cuales fueron los commits que se hicieron en un commit especifico, se puede hacer de la siguiente manera.

`git log --after="yyyy-mm-dd"`