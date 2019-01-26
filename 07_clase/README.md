# Clase 7

## Fusiones
Se crea una rama para hacer una nueva caracteristica en el proyecto. Y cuando ya la hemos probado, la funcion de esta nueva caracteristica, lo que hacemos es fusionarla y agregarla a la rama principal del "proyecto"; sin embargo a pesar de que es una rama ya hace parte del proyecto.

El flujo normal es, crear una rama, agregar una nueva funcionalidad en ella y una vez terminada, la fusionamos a la rama principal. Una vez eliminada, podemos eliminar esa rama.

Para poder fusionar una rama, nosotros utilizamos el comando `git merge <otra rama>`

Agarra la otra rama y la fusiona en la rama en la que estamos actualmente. 

Se pueden fusionar ramas a cualquiera otra. No necesariamente a la mas cercana. Suele hacerce o suele ser comun que se haga a la rama mas cercana.

Cuando se hace una rama de una rama, suele ser porque la subrama es una subcaracteristica de una rama, por eso puede que esa subcaracteristica se fusione a la rama de la caracteristica, para luego fusionarse con la rama master.

Una vez terminada la caracteristica, tenemos que ubicarnos en la rama destino Si nosotros queremos que los cambios terminados esten en master tenemos que ubicarnos en master. Una vez hecha la fusion, podemos eliminar la rama. Cuando eliminamos la rama, solo estamos eliminando el apuntador, pero no los cambios, los cambios de los commits seguiran existiendo. Cuando eliminamos una rama *Solo se elimina el apuntador*. Pero los commits siguen estando ahi, ahora hacen parte de master.

Si queremos elimniar una rama, Si estamos completamente seguros de que los cambios en esa rama no son necesarios (y no la hemos fusionado aun) `git branch -D` *los cambios se van a perder*. Sin embargo; la opcion ideal siempre es `git branch -d` 

Ahora bien con el comando `git branch --no-merged` nos dira cuales son las ramas que no hemos fusionado con la rama actual. 

# LOS CONFLICTOS
muchas veces nos toparemos con conflictos, la mayoria de veces cuando se trabaja en equipo. Un conflicto se genera cuando dos ramas separadas modifican la misma linea del mismo archivo, es cuando se presentan los conflictos. Ahora git, no sabe a cual de las dos ramas hacerle caso. Porque las dos ramas estan modificando las mismas lineas. Git toma eso como un conflicto y nos dice, decida usted cual es el cambio correcto. Cual de las dos ramas hacerle caso para esa misma linea que las dos modificaron.

*Basicamente son dos ramas que se quieren fusionar que han modificado la misma linea en el mismo archivo*

Si intentamos dar un merge y nos aparece un conflicto nos avisara que tenemos que resolver el conflicto antes de hacer el merge. Posteriormente, si hacemos un `git status` nos aparecera `both modified: <file_name>` que el archivo se ha modificado en las dos ramas.

Se tiene que resolver el conflicto manualmente. Si nos ubicamos en el archivo nos apareceran tres lineas

* `<<<<<<< HEAD`
* `=======`
* `>>>>>>> testing`

Estas tres lineas nos engloban el conflicto en cuestion. Nos dice que en la rama actual `HEAD` esta la linea de abajo. y en la otra rama en la misma ubicacion estan las otras dos lineas. Entonces se separa de la siguiente manera.

```git
<<<<<< HEAD
Esto es lo que se encuentra en el archivo actual
=======
Esto es lo que se encuentra en el otro archivo que se quiere fusionar.
>>>>>> testing
```

Para nosotros resolver este conflicto, tenemos que remover manualmente lo que no queremos o dejar ambas cosas si es asi lo decidimos. Lo unico que hacemos es quitar los señaladores. Guardo los cambios y si hago un git status me va a seguir apareciendo un `both modified`. Para nosotros concluir la solucion del conflicto tenemos que hacer un commit del both modified. Luego del commit. el merge estara completo. 

El la mayoria de los proyectos puede que en lugar de utilizar tags se utilicen ramas para solucionar, bugs o errores o issues, de un proyecto y mantener esa version. Un ejemplo puede ser drupal, en estos momentos esta en la version 8, y puede que muchos desarrolladores esten aun trabajando en la version 7, desarrollando nuevas caracteristicas para esa version, entonces esa version 7 deberia seguir construyendo su camino. Asi que entre versiones suele utilizarse como una nueva rama para que siga su camino, el tag no es suficiente. El tag solo esta creando un punto en la historia y nosotros necesitamos que sea una nueva rama que vaya incorporando las soluciones a los posibles errores que aun tengan los desarrollos para drupal 7. 

Si llega un momento en que se nos olvido o la posibilidad no la contemplamos, seguir un mismo camino para la version de nuestro proyecto podemos o ir a ese punto en el tiempo. Crear una rama a partir de ese punto en el tiempo, y si una etiqueta ya nonos sirve entonces la eliminamos.

