# Git

Git es el sistema de control de versiones más popular del mundo. Puede mantener un historial completo de los cambios realizados en el código y volver a versiones anteriores cuando sea necesario. Estas características son útiles cuando se desean realizar cambios en el código sin perder el original.

Git también facilita la sincronización de código entre diferentes personas, lo que facilita enormemente la colaboración en equipo. Esta característica conduce a un aumento de la productividad, en particular en grandes proyectos de software que involucran a muchos desarrolladores.

# Conceptos


**Repositorio**: una colección de archivos rastreados por Git. Los archivos que componen el contenido de este grupo de notas se guardan en un repositorio Git.

**Commit**: Git no guarda ningún cambio realizado en los archivos dentro de su repositorio hasta que realice un *"commit"*. Entonces, como verbo, es la acción de almacenar una nueva instantánea del estado del repositorio en el historial de Git. Cuando se usa *"commit"* como sustantivo, se refiere a un solo punto en la historia de Git.

**Staging**: Expliquemos este con un ejemplo; Supongamos que se realizaron cambios en 4 archivos dentro de su repositorio, pero solo desea confirmar 2 de ellos porque los otros 2 tienen errores o aún no están completos. ¿Cómo se puede realizar el commit de solo 2 archivos? Bueno, hay que ponerlos en el "área de staging" después de lo cual es posible realizar un commit. Entonces, realizar un staging en un archivo significa que lo ha marcado para una confirmación.

# Instalar Git

Siga las instrucciones proporcionadas en este [enlace](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) para configurar Git en su computadora portátil o computadora personal.

# Usando Git localmente

Abra una terminal en su sistema operativo.

En primer lugar debe comprobar si Git está instalado

```
git --version
```

Debe indicarle a Git quien es

```
git config --global user.email "nombre@ejemplo.com.ar"  
git config --global user.name "nombre"
```

Configure e inicie un nuevo repositorio

```
cd path/directorio/de/trabajo
mkdir nombre_repositorio
cd nombre_repositorio
git init
```

Git no esta rastreando todos los cambios dentro de la carpeta ```nombre_repositorio```.

Agregue un archivo a su área de staging

```
touch README.md
git status
```

Con este último comando deben obtener un listado de **archivos sin seguimiento**.

Ahora, si ejecuta los siguientes comandos, debe obtener una lista de "Cambios a confirmar". Al usar ```git add .```, se agregan todos los archivos *(que no se encuentran en estado de staging)* en su repositorio en el área de staging.

```
git add .
git status
```

> No es necesario utilizar ```git status``` cada vez que ejecuta un comando en Git. En este caso se ha usado para demostrar como va cambiando el estado de un archivo.

Confirmando los archivos (Commit)

```
git commit -m "mensaje asociado al commit"
git status
```

Comprobando el historial de confirmaciones

```
git log
```

Las primeras líneas representan archivos que se modificaron o agregaron, los números después del campo de commit representan el valor hash del commit *(una cadena única que identifica la confirmación)*. Los campos Autor y Fecha contienen información sobre el autor, la hora del commit y el mensaje que el autor envió con el commit.

# Ejercicios

**Ejercicio 1**
 
Abra el archivo ```README.md``` en su editor de texto favorito. Agregue su nombre y luego guarde el archivo.
 
Regrese a la terminal y ejecute ```git status```, ¿Git es lo suficientemente inteligente como para darse cuenta de que ha realizado un cambio en el archivo README.md?
 
Ejecute los comandos anteriores para agregar y confirmar los cambios realizados en el archivo ```README.md``` al historial de Git.

Ejecute ```git log``` nuevamente, ¿cuántas confirmaciones tiene?

**Ejercicio 2**
 
¿Puede revertir el cambio realizado en el archivo ```README.md```?


