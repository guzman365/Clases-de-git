# clase 6, las ramas.

Las ramas, son como mundos paralelos, nuevos caminos por los que puede ir la historia

### Una rama y su historial de confirmaciones.
![ramas de git](/img/branch-and-history.png)

Una rama de git es un apuntador, pero este es movil, porque se va a mover con las confirmaciones que se vayan haciendo. La rama por defecto es master y sera la rama principal. master es un apuntador a un commit.

Las ramas, a diferencia de las etiquetas, las ramas se mueven, si nosotros hacemos un nuevo commit, el commit va a estar apuntado por master. master no es que sea una rama principal, solo es una rama. No siempre tiene que llamarse master. Se llama master por defecto, pero lo podriamos cambiar si quisieramos. 

### Dos ramas apuntando al mismo grupo de confirmaciones
![Dos ramas](/img/dos_ramas.png)

Podemos tener varias ramas, apuntando al mismo commit.

Para crear una rama procedemos con el siguiente comando `git branch <nombre_rama>`

### Apuntador HEAD a la rama donde estamos actualmente.
![Apuntador head](/img/apuntador_head.png)

HEAD siempre tiene la fechita apuntando hacia la rama donde nos encontramos, por defecto esta apuntando a master, hacia la rama.

*HEAD, nos indica donde estamos nosotros parados. Este es un apuntador especial, podemos cambiarle el nombre a master, pero no a HEAD.*

### El apuntador HEAD apunta a la rama actual
![apuntador head](/img/head-to-testing.png)

Que pasas si nosotros creamos un nuevo commit, estando en una rama diferente. Avanzamos en el tiempo, nuevas confirmaciones, pero testing es el apuntador que se va a mover. Master es el apuntador que se quedara con el commit indicado, hasta que nosotros nos movamos y hagamos commits de master.

### La rama apuntada por HEAD avanza con cada confirmacion de cambios
![la rama apuntada por HEAD avanza](/img/advance-testing.png)

si se confirman los cambios en una rama diferente que master. El head nos se seguira moviendo a medida hagamos commits. PEro el master siempre seguira en el mismo punto.

### HEAD apunta a otra rama cuando hacemos un salto
![HEAD salto Master](/img/head_salto_master.png)

Podemos mover el apuntador HEAD hacia master, que basicamente quedo en el pasado. podemos `git checkout master`

*PARA MOVERNOS ENTRE RAMAS, NUESTRA AREA DE TRABAJO DEBE DE ESTAR LIMPIA, EN LA MEDIDA LO POSIBLE, HAY EXCEPCIONES, PERO SIEMPRE HAY QUE ACOSTUMBRARSE A TENER EL AREA DE TRABAJO LIMPIO.*

### Los registros de las ramas divergen
![Ramas_divergen](/img/ramas_divergen.png)

Ya se tienen dos universos el universo master y el universo testing dos ramas que pueden avanzar cada una por su lado. Testing esta mas adelante que master. Si se hace un commit en master, master seguira su propio camino eso quiere decir que se tendria algo como la imagen de arriba. 

Cuando se hace un checkout a un proyecto, estamos yendo al estado de ese proyecto en ese momento en ese punto en la historia. 

Por ejemplo si viajamos en un punto en nuestra historia donde nosotros no existiamos. Es lo mismo con los archivos, si los archivos no existen en ese momento, no apareceran en el proyecto. 

Se pensaria de que solo se puede sacar ramas de la linea principal de tiempo, cada una de estas ramas, simplemente son apuntadores a un commit. Por lo que de esta forma todos los commits van hacia adelante, se puede decir de que van uno a tras de otro. Por lo tanto podemos seguir avanzando sin importar en que rama estemos, y dependiendo en que rama estemos, podemos crear una nueva rama.

No importa en que rama estemos, podemos crear una rama a partir de ella, si es lo que queremos y si conviene.

*Llegara un momento, en el que nos damos cuenta que los cambios de la rama, ya estan terminados, porque que es una rama, es un universo paralelo, pero para que los utilizamos entonces? nosotros utilizamos esas ramas para crear una nueva caracteristica de nuestro proyecto, cuando esa caracteristica nueva que hemos creado ya esta lista nosotros queremos integrarla a una rama principal, que la rama principal puede tener cualquier nombre, pero es muy comun que se llame master. Yo podria decidir que mi rama princiap de este proyecto, siempre seria la rama universo3, y que la otras ramas solo son caracteristicas que le quiero agregar a mi universo 3*

*En un proyecto real esto va a ser una caracteristica del sistema. Login del sistema, se creo el login del sistema, luego de que probamos de que esa nueva caracteristica que se hizo, funciona y no falla, se hizo test entonces se puede agregar esa rama y unirla a esa rama principal. Para que la linea de tiempo principal ya tenga esa funcionalidad de login, ESO ES MEZCLA DE RAMA | FUSION DE RAMAS*