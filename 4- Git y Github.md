# Git

Git es el sistema de control de versiones más popular del mundo. Puede mantener un historial completo de los cambios realizados en el código y volver a versiones anteriores cuando sea necesario. Estas características son útiles cuando se desean realizar cambios en el código sin perder el original.

Git también facilita la sincronización de código entre diferentes personas, lo que facilita enormemente la colaboración en equipo. Esta característica conduce a un aumento de la productividad, en particular en grandes proyectos de software que involucran a muchos desarrolladores.

# Conceptos


**Repositorio**: una colección de archivos rastreados por Git. Los archivos que componen el contenido de este grupo de notas se guardan en un repositorio Git.

**Commit**: Git no guarda ningún cambio realizado en los archivos dentro de su repositorio hasta que realice un *"commit"*. Entonces, como verbo, es la acción de almacenar una nueva instantánea del estado del repositorio en el historial de Git. Cuando se usa *"commit"* como sustantivo, se refiere a un solo punto en la historia de Git.

**Staging**: Expliquemos este con un ejemplo; supongamos que se realizaron cambios en 4 archivos dentro de su repositorio, pero solo desea confirmar 2 de ellos porque los otros 2 tienen errores o aún no están completos. ¿Cómo se puede realizar el commit de solo 2 archivos? Bueno, hay que ponerlos en el *"área de staging"* después de lo cual es posible realizar un commit. Entonces, realizar un staging en un archivo significa que lo ha marcado para una confirmación.

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

Que retorna algo semejante a lo siguiente

```
commit 19d248fddb0b2c71aded0922d29961a817f5bb66 (HEAD -> master)
Author: cbiale <claudio_biale@yahoo.com.ar>
Date:   Mon Sep 14 19:28:34 2020 -0300

    prueba 1
```

Los números después de commit representan el valor hash del commit *(una cadena única que identifica la confirmación)*. Los campos Autor y Fecha contienen información sobre el autor, la hora del commit. Luego se especifica el mensaje que el autor envió con el commit.

# Comandos

`git config user.name`: devuelve el nombre de usuario.

`git config user.email`: devuelve el email de usuario.

`git add <nombre(s) de archivo>`: agrega archivos al área de staging para ser incluidos en la próxima confirmación.

`git add .`: agrega todos los archivos del directorio.

`git commit -m "mensaje"`: toma una instantánea del repositorio y la guarda con un mensaje asociado a los cambios.

`git commit -am <nombre(s) de archivo> "mensaje"`: agrega archivos y confirma los cambios, todo en uno.

`git status`: imprime el estado actual del repositorio.

`git log`: imprime un historial de todos los commits *(confirmaciones)* que se han realizado.

`git checkout <commit>`: permite ver el estado de un repositorio en un commit *(confirmación)* determinado.

`git checkout <commit> -b <nombre rama>`: crea una nueva rama de acuerdo al estado de un repositorio en un commit *(confirmación)* determinado.

`git revert <commit>`: revierte un commit *(confirmación)* determinado, guardando la acción en el historial.


# Ejercicios

**Ejercicio 1**
 
Abra el archivo ```README.md``` en su editor de texto favorito. Agregue su nombre y luego guarde el archivo.
 
Regrese a la terminal y ejecute ```git status```, ¿Git es lo suficientemente inteligente como para darse cuenta de que ha realizado un cambio en el archivo README.md?
 
Ejecute los comandos anteriores para agregar y confirmar los cambios realizados en el archivo ```README.md``` al historial de Git.

Ejecute ```git log``` nuevamente, ¿cuántas confirmaciones tiene?

**Ejercicio 2**
 
¿Puede revertir el cambio realizado en el archivo ```README.md```?

# Lecturas recomendadas

Para aprender sobre git pueden acceder a: [git](https://git-scm.com/doc) o [git-tower](https://www.git-tower.com/learn/) 

Si quieren una hoja de referencia pueden usar la [Hoja de referencia para Github Git](https://training.github.com/downloads/es_ES/github-git-cheat-sheet/) ([pdf](https://training.github.com/downloads/es_ES/github-git-cheat-sheet.pdf))

# Github

Antes de hablar sobre GitHub, deben tener en cuenta el hecho de que Git y GitHub no son lo mismo. Git es un sistema de control de versiones, mientras que GitHub es un servicio de alojamiento de repositorios y una plataforma de colaboración.

> Deben crear una cuenta en github.com *(si aún no tienen una)*.

# Temas a considerar

Usaremos GitHub ampliamente en este curso:
- para alojar sus proyectos, 
- como una plataforma en la que pueden realizar trabajo colaborativo,
- para proporcionarle comentarios sobre su trabajo, 
- etc.

Deben comprender *(y usar)* el funcionamiento de GitHub en cuanto a:

- Comunicarse usando issues *(propuestas)*.
- Crear ramas *(para agregar/actualizar funciones o características)*.
- Realizar un pull request para introducir cambios.
- Fusionar cambios.

# Tarea a realizar

Deben completar el curso denominado [Introducción a GitHub](https://lab.github.com/githubtraining/introduction-to-github) *(es práctico y tiene una duración de aproximadamente media hora)*.

# Comandos y conceptos útiles

**Repositorios**: Un **repositorio remoto** es aquel que no esté almacenado localmente en un dispositivo *(Entonces, GitHub es un servicio para alojar repositorios remotos )*. Un **repositorio de origen**  es aquel repositorio remoto desde el que se descargó originalmente el repositorio local.

`git clone <url>`: toma un repositorio almacenado en un servidor *(como GitHub)* y lo descarga.

`git push`: envía los cambios locales *(confirmaciones o commits)* a un servidor remoto.

`git fetch`: descarga todo el historial de confirmaciones desde un repositorio remoto a un repositorio local.

`git pull`: descarga cualquier cambio remoto de un repositorio remoto a un repositorio local.


**Fusiones**: cuando se combinan diferentes versiones de código, por ejemplo, al usar  `git pull`, puede ocurrir un conflicto de fusión si las diferentes versiones tienen diferentes datos en la misma ubicación. Git intentará encargarse de la fusión automáticamente, pero si dos usuarios editan, por ejemplo, la misma línea, un conflicto de fusión deberá resolverse manualmente.

> Para resolver un **conflicto de fusión**, simplemente elimine localmente todas las líneas y el código que no se desee y realice un `push`.

Cuando se trabaja en equipo, es responsable de resolver el conflicto aquella persona que realizo por última vez un `push` y por lo tanto desencadenó el conflicto.

**Ramas**: La ramificación es una característica de Git que permite que un proyecto se mueva simultáneamente en varias direcciones diferentes. Hay una rama `master`  que siempre se puede utilizar, pero se pueden crear cualquier número de ramas nuevas para desarrollar nuevas funciones. Una vez que estén listas, estas ramas se pueden fusionar nuevamente en  `master`.


> Cuando trabajamos en un repositorio Git , **HEAD** se refiere al último commit de la rama actual donde se está trabajando.  Pero si nos movemos hacia cualquier otro commit  entonces el HEAD cambia para indicar la nueva rama de trabajo.

> Al fusionar una rama de nuevo en master, existe la posibilidad de que surjan conflictos de fusión.


`git branch`: enumera todas las ramas actuales de un repositorio.

`git branch <nombre rama>`: crea una nueva rama.

`git checkout <nombre rama>`: cambia la rama de trabajo actual a la especificada.

`git merge <nombre>`: fusiona la rama especificada en la rama de trabajo actual *(normalmente  master)*.

`git merge origin/master`: fusiona `origin/master`, que es la versión remota de un repositorio que normalmente se descarga con  `git fetch`, en la rama local `master`.

`git pull` es equivalente a ejecutar un `git fetch` y luego un `git merge origin/master`.

# Issues

La mayoría de los proyectos de software tienen algún tipo de rastreador de errores. El rastreador de GitHub se llama *issues* y tiene su propia sección en cada repositorio. Aunque originalmente estaba destinado a rastrear errores, las *issues* ahora se utilizan para realizar un seguimiento de las mejoras, la hoja de ruta del producto, para la planificación, las solicitudes de funciones, etc. Las *issues* están en el corazón de GitHub y actúan como una especie de sala de chat/foro/correo electrónico donde todos los miembros de su equipo de trabajo pueden comunicarse sobre su proyecto de software.

# Fork

Una fork o bifurcación de un repositorio es un repositorio completamente separado que es una copia del repositorio original. Un repositorio bifurcado se puede administrar y modificar como cualquier otro, todo sin afectar la copia original.

Los proyectos de código abierto a menudo se desarrollan utilizando bifurcaciones. Habrá una versión central del software que los contribuyentes bifurcarán y mejorarán, y cuando quieran que estos cambios se fusionen en el repositorio central, envían una "solicitud de extracción" *(pull request)*.

> En este curso no vamos a utilizar bifurcaciones

# Pull request

Se puede realizar una solicitud de extracción *(pull request)* para fusionar una rama de un repositorio con otra rama del mismo repositorio o incluso con un repositorio diferente. 

> Las bifurcaciones, las issues y las solicitudes de extracción son características específicas de GitHub.
