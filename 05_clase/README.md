# Clas 5

## Las etiquetas.
Las etiquetas en Git sirven para marcar puntos especificos en la historia como importantes, es como poner un marcador, o ponerle algo que le indentifique, Para no tener que aprendernos la suma de comprobacion o checksum.  

*Ejemplo* si queremos hacer referencia a que un punto en la historia esta bien, o esta trabajando bien, o es la version 1.0 de nuestro proyecto. para eso se crea una etiqueta.

## git tag
Lista de etiquetas.

Este comando lista las etiquetas en orden alfabetico; el orden en el que aparecen no tiene mayor importancia.

## Hay dos tipos de etiquetas; etiquetas ligeras y etiquetas anotadas

### Etiqueta ligera
`git tag v1.1-dev`

Una etiqueta ligera no es mas que el checksum de un commit guardado en un archivo, no incluye mas informacion. Para crear una etiqueta ligera, no pasamos las opciones -a, -s ni -m:

Solo es un apuntador a un commit, es decir que podriamos verlo como un alias de una de esas sumas de comprobacion, de uno de esos checksum.

Si se crea de la forma de arriba la etiqueta se agregara al commit mas reciente. Para mostrar las etiquetas a que commit pertenecen, se muestran con un `git log`

Se pueden crear etiquetas no solo en el ultimo commit que se hizo. Se puede agregar en cualquier punto o commit. Pero es muy recomendable utilizar las etiquetas anotadas.

## Etiquetas anotadas.
`git tag -a v1.0 -m 'my version 1.0'`

Se guardan en la base de datos de Git como objetos enteros. Tienen un checksuml contienen el nombre del etiquetador, correo electronico y fechal y tienen un mensaje asociado. Es casi como un commit, un commit en un punto en la historia.(un commit del commit). En las etiquetas anotadas, podemos colocar un mensaje con los cambios que han habido hasta ese punto en la historia. Son sumamente utiles cuando queremos marcar las versiones de nuestro proyecto. LAs etiquetas pueden tener cualquier nombre, *no se admiten espacios en blanco*. Se suele utilizar v para la version -m para poder mandarle un mensaje. Sino le pasamos la opcion -m entonces git abrira el editor que nosotros tengamos configurado. PAra que escribamos el mensaje debido a que es obligatorio. 

* -a para decir que es una etiqueta anotada.

## Diferencia entre etiqueta anotada y ligera.
Cuando usar una u la otra? LAs etiquetas ligeras debido a que son una referencia rapida, nos servirian no tanto para las versiones del proyecto, como la version 1.0 2.0 etc. Sino para marcar pequeñas funcionalidades que aun estan en desarrollo, para volverlas una version. 

Aparentemente, cuando se muestra el git log, son similares. Pero como es eso que una se guarda en la base de datos y la otra es un apuntador? Si yo quisiera ver una etiqueta especifica utilizo `git show <tag>`, muestra el commit junto con los cambios relacionados para una etiqueta ligera. 

En una etiqueta anotada, me muestra la informacion de la etiqueta, quien es el etiquetador, la fecha en la que se creo esta etiqueta, y el mensaje de la etiqueta, junto con el commit y la informacion del commit, con el autor del commit, que no necesariamente tiene que ser el que creo la etiqueta. 

Asi mismo para poder crear una etiqueta que no sea la ultima de los commits se utiliza `git tag ignorados-iniciales <checksum>`. Se pueden crear etiqueta anotadas si le pasamos `-a`.

Es posible que estemos ante un proyecto muy grande con bastante historial y que tengamos muchas etiquetas como "1.0.1", "1.0.2" Etiquetas que tienen en comun ciertas partes partecitas. Por ejemplo que todas las versiones 1.0.algo. Queremos filtrarlas. Podemos agregar al listado de etiquetas para que solo nos liste ese patron que nos interesa, porque podemos llegar a tener muchas etiquetas en nuestro proyecto, con el paso de los años con el paso del tiempo. 

Quisiera las etiquetas que correspondan a la version 1, para ello se utilizan patrones `git tag -l "1.*"`

Asi mismo cabe recalcar que se puede hacer un checkout con una etiqueta `git checkout <tag>`.

