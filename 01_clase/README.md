# GIT

*Sistema de control de versiones*

*Maquina de tiempo*

Si ustedes hacen una cosa y confirman ese cambio, ese cambio va a quedar grabado en la maquina de tiempo. la clave es confirmar.

Si estamos documentando algo en word, y borramos algo, recurrimos al `control + z`, de manera subjetiva estamos regresando en el tiempo, en puntos anteriores, y si vamos a reacer estamos llendo para adelante. Esa es una pequeña aplicacion que simula lo que viene siendo un sistema de control de versiones.

En git, todos los cambios, asi se cierre el programa, computadora y o donde se encuentre, siempre podra regresar en el tiempo atras a los cambios que se hayan hecho, y a parte de eso van a poder mezclar las cosas. mezclar cambios de determinados puntos en el tiempo.

## Estados de git

Working Directory (directorio de trabajo)
: Es donde nosotros tenemos los archivos, es decir la raiz. Todo lo que haya dentro de la carpeta de nuestro projecto.

Staging Area (Area de preparacion)
: Contiene todos los archivos que nosotros decimos, listo, ya estan preparados para poder confirmar esos cambio. Para poder fijarlos en un punto en el tiempo. 

.git directory (repository) directorio.git(repositorio)
: Es donde estan los cambios confirmados, la linea de tiempo como tal. 

## Flujo de trabajo basico en Git

1. Modificas una seria de archivos en tu directorio de trabajo.
2. Preparas los archivos, añadiendolos a tu area de preparacion
3. Confirmas los cambios, lo que toma los archivos tal y como estan en el area de preparacion y almacena esa copia instantanea de manera permanente en tu directorio de Git.

## Configurando Git por primera vez.

* `git config --global user.name "Mau Reyes"`
* `git config --global user.email "mreyes@gmail.com"`
* `git config --global core.editor nano`
* `git config --list`

## Obtener ayuda

* `git help <verb>`
* `git <verb> --help`

*ejemplo*

`git help config`

`git config --help`