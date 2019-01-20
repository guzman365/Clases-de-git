# Clase 4

## Comandos para deshacer

Para rehacer la confirmacion 

`git commit --amend` Este comando utiliza el area de preparacion para la confirmacion.

Al final terminaras con una sola confirmacion - la segunda confirmacion reemplazara el resultado de la primera.

Este es si alguna razon, hicimos un commit y se nos olvido agregar un ultimo archivo a este commit, y dejarlo por fuera para hacer un nuevo commit no seria tan conveniente, para el historial. 

el comando --amend va a tomar todo lo que hay en el area de preparacion y lo agregara en el ultimo commit. Lo que se hara es reemplazar el ultimo commit.

ESto es para las metidas de pata. 

*Usualmente cuando hacemos un commit, usualmente esta relacionado con una funcionalidad o una caracteristica especifica que puede involucrar varios archivos y dejarlo a parte no es una buena practica.*

## git reset HEAD <file>
El archivo o los archivos salen del area de preparacion y se quedan en el directorio de trabajo. 

Esto tambien nos sirve por si en alguna razon se crea un archivo cualquiera, nuevo archivo y se me da de agregar todos los archivos al area de preparacion con `git add .` y tengo los dos archivos en el area de preparacion, pues esto no es lo que quiero, necesito hacer un commit, solo de el primer archivo. 

## git checkout -- file
**Descarta un archivo modificado**

Este es un comando peligroso

Cualquier cambio que le hayas hecho a un file desaparecera.

Nunca utilices este comando a menos que estes absolutamente seguro de que ya no quieres los cambios del archivo.

___

Cuando vamos a utilizar una libreria o simplemente queremos participar en un proyecto colaborativo o codigo libre. Nos encontramos con que nos dicen "clonen el repositorio"

lo haremos utilizando el repositorio de edteam 

<https://github.com/escueladigital/ED-GRID>

Note: que al momento de clonar el repositorio desde git clone, ahi vienen todos los commits. Sin embargo, si se quiere descargar .zip, los commits no se encuentran por la ausencia del directorio `.git`. Esa es la diferencia entre git clone y descargar el proyecto. 

___
**Lo siguiente es nada mas una referencia**
c8e998a (HEAD -> master, origin/master, origin/HEAD)

el HEAD quiere decir que estamos parados en la rama master.

**donde se encuentra en HEAD, es basicamente el presente para nosotros. si viajamos al pasado, ese pasado ene se momento sera el presente para nosotros.**
___

## Primer salto en el tiempo

Si regresamos a un punto en en la historia de nuestros commits de git. Todos los commits luego del que regresemos, seran eliminados de nuestra area de trabajo.

Para poder ver las diferencias entre los commits o entre dos puntos para saber que e slo que realmente va a desaparecer.

`git diff <hash1> <hash2>`

Nos muestra en rojo las cosas que eliminamos, y nos muestra en verde las cosas que agregamos.

Para poder viajar en el tiempo o regresar a cierto punto de nuestro historial acumulado en git.

`git checkout <hash>`

Para regresar al presente, tenemos que que regresar a master

`git checkout master`

Asi mismo, se puede etiquetar los hash para que no tengamos que recordar o estar copiando los hash.

___
*Cuando se regresa a un punto en la historia y no se logran ver todos los archivos, es porque esos archivos no existian en ese momento. Y cuando no se logran ver los archivos uno tiende a hacer muchas tonterias, una de ellas es volver a clonar el repositorio y volver a hacer los cambios y rehacer cosas, **Horas de trabajo** cuando dichos cambios ya estan en el repositorio.*
___


Consultar el historial es necesario para saber adonde es que estamos parados, y si hay mas historia por encima de nosotros, ESTO es importante cuando trabajamos con repositorio remoto con otros desarrolladores con un equipo, con otras personas. Porque puede que nosotros estemos en un punto de la historia, y nuestros compañeros esten avanzando con sus propios cambios y entre ellos ya esten mas arriba de la historia. Esto suele pasar y pasa, por eso hay que estar pendiente en que punto de la historia estamos y ver si ya tenemos los cambios de nuestros compañeros y si ellos tambien tiene los nuestros ellos verifican asi. 