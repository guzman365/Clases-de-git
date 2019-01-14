# Guardando cambios en el repositorio

Nosotros podemos inicializar el repositorio git, eso lo podemos hacer habiendo o no carpetas o archivos en el directorio. Esto se logra con `git init`. Al correr este comando, se crea la carpeta **.git** donde se encuentra la base de datos de cambios de git y aqui es donde vamos a poder acceder al historial. No significa que tengamos que acceder a esta carpeta para hacerlo. Por los comandos que utlizamos git es quien accede a esta carpeta.

**NOTA**: Es recomendable que se cree un readme.md, porque este es el index que lee github. Asi que es una buena practica tener este archivo.

Nosotros podemos seguir cualquier archivo, puede ser una imagen, una archivo html, php, go, java... Cualquier archivo lo podemos trackear.

Si se efectua un cambio en cualquier repositorio y se corre el comando `git status` muestra el estado del respositorio. Todos los archivos que no se estan siguiendo, todos los archivos que estan en el area de preparacion.

Si se tienen archivos que no se estan siguiendo, el comando para poder seguir dichos archivos es `git add <file>`. Esto es el area de preparacion, osea los archivos que estan listos para ser commiteados o confirmados.

Para poder commitear los cambios o para confirmarlos entonces procedemos con `git commit -m "mensaje"`. No necesasriamente los commits deben de ser de un solo archivo, un commit puede tener varios archivos.

Para poder ver las confirmacion que se han realizado (commits) se usa el comando `git log`

Al momento de verificar el estado de tu directorio, te podrias preguntar cuales son los cambios de un archivo. Esto se puede lograr con `git diff`. 

Que pasa si un archivo estando en el area de preparacion se le hacen cambios? Basicamente aparecera el mismo archivo o archivos dos veces, Uno en el area de trabajo y otro en el area de preparacion.

Al momento que le dimos `git add` esos son los cambios que estan hasta ese punto fueron los que se prepararon para confirmarse. Osea que que el readme.md que esta en el area de preparacion no tendra los cambios del archivo que esta en el area de trabajo.

Ahora bien, si se ejecuta `git diff` se mostraran los nuevos cambios efectuados en el archivo.

Si se tiene el mismo archivo en el area de trabajo y area de preparacion, y si hacemos un `git add` el archivo que esta pasando al area de preparacion sobreescribira el que esta en el area de preparacion.

*Podemos modificar cualquier parte del archivo*

Si es que existen muchos archivos y se quieren agregar todos los archivos al area de preparacion es `git add .`

Si se quiere sacar un archivo del area de preparacion lo que tenemos que hacer es `git reset HEAD <filename>`

En dado caso se quiere cambiar el mensaje de un el ultimo commit(en este caso) porque se cometio un error en dicho mensaje, se utiliza el siguiente commando. `git commit --amend`

## Ciclo de vida del estado de nuestros archivos.

![Git life cicle](../img/lifeciclegit.png)

## .gitignore

Patrones de nombres de archivos que git ignorara

[gitignore](https://gitignore.io)

Hay que tener cuidado ya que aveces esta herramienta ensucia de cierta manera, porque hay muchos patrones que nunca se van a utilizar. Es mejor planearlo y hacer el suyo propio. 
