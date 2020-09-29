# Manejo de dependencias con Maven

Vamos a hacer un rápido recorrido de una popular herramienta de automatización de compilación denominada **Maven**. Las herramientas de compilación se utilizan para automatizar el proceso de empaquetar y enviar su código a sus usuarios. Cuando se trabaja con equipos, es esencial tener una herramienta de construcción estandarizada.

Maven  es una forma  moderna  de  construir  un  proyecto en Java *(aunque Gradle esta ganando terreno)*. Al  igual  que un makefile en C, en Maven es posible definir fases para diferentes funciones del ciclo de vida, para ello existe un archivo de configuración denominado **pom.xml**.

Entre las opciones se encuentran:
- clean: limpia los artefactos creados por compilaciones anteriores
- validate:  asegurarse  que  se  tienen  por  ejemplo  todos  los  paquetes  requeridos, etc.
- compile: compila el código fuente del proyecto
- test: realiza  pruebas del  código  fuente  compilado  usando  un framework de prueba.
- package: poner todo en un único archivo, por ejemplo un archivo jar.- install:instala  el  paquete  en  el  repositorio  local,  para  usarlo  como  dependencia en otros proyectos localmente
- site: genera documentación.
- deploy: se  realiza en  un  entorno  de  integración,  copia  el  paquete final  en  el repositorio remoto para compartirlo con otros desarrolladores y proyectos.


> [Gradle](https://gradle.org/) es otra alternativa en Java.

En esta materia, vamos a limitar nuestro enfoque en la gestión de dependencias. Al crear aplicaciones de software, a menudo se utilizan herramientas y bibliotecas escritas por otros desarrolladores. Estos programas de software son las dependencias de su aplicación, ya que su software *(o flujo de desarrollo)* depende de él. Por ejemplo, al crear un proyecto Java en VSCode se utiliza JUnit pruebas unitarias. JUnit es un programa de código abierto escrito para facilitar el desarrollo basado en pruebas en Java.

Cuando una dependencia que está utilizando requiere otra biblioteca, la biblioteca requerida se convierte en una dependencia transitiva. Esencialmente, lo que esto significa para usted es que también depende de esa otra dependencia. A medida que su proyecto se vuelve más grande y el código más complejo, necesitará una herramienta para administrar todas las dependencias.

En este punto entran en juego **Maven**, que ante todo es una herramienta de construcción, pero también hace un gran trabajo en la gestión de dependencias. 

El  uso  de  este  tipo  de  herramientas  es  clave  para  los  proyectos,  dado  que  se  puede compartir un  archivo  de  compilación  de  Maven  y el equipo de  desarrollo utilizará automáticamente  versiones  idénticas  de  bibliotecas,  etc.,  minimizando de  esta  forma errores.

## El archivo pom.xml

Es  el  núcleo  de  la  configuración  de  un  proyecto  en  Maven.  Es  un  archivo  de configuración único que contiene la mayoría de la información requerida para construir un proyecto de la manera que se desee.

## Agregar dependencias

Es posible buscar dependencias en repositorios Maven para agregarlas a nuestro archivo pom.xml en sitios como https://mvnrepository.com/.

Por ejemplo si se quiere agregar JUnit 5 a nuestro proyecto Maven debemos ingresar en la caja de búsqueda del sitio web: *junit*, lo cual nos devuelve un conjunto de resultados.

Debemos seleccionar el resultado que concuerda con lo buscado y seleccionar la versión a utilizar.

Realizado esto, nos aparece un detalle del código que debemos agregar en las dependencias del archivo pom.xml, en este caso:

```
<dependency>
    <groupId>org.junit.jupiter</groupId>
    <artifactId>junit-jupiter-api</artifactId>
    <version>5.5.2</version>
    <scope>test</scope>
</dependency>
```

Esto se debe agregar en el apartado **dependencies** del archivo pom.xml del proyecto.

> Referencias adicionales:
> 
>- [Java build tools in VS Code](https://code.visualstudio.com/docs/java/java-build)
> - [Maven Introduction](http://maven.apache.org/what-is-maven.html)
> - [Maven in 5 Minutes](https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html)

# Recomendación de cursos

El proyecto consiste en crear un sitio web donde las personas puedan comentar y calificar los cursos que han realizado. El sitio está destinado a ser un portal para la comunicación de persona a persona, facilitando la comunicación entre sí para averiguar qué cursos tomar *(y cuáles evitar)*.

El proceso de revisión debe ser seguro, sencillo y ágil. Una persona podrá agregar un curso que haya tomado y escribir una breve reseña del mismo. La revisión debe incluir una calificación de cero a diez, un comentario sobre su experiencia y un consejo para las personas que consideren tomar el curso *(qué esperar del curso, cómo tener éxito, etc.)*.

> Piense en la **especificación de requisitos del proyecto**.

> **Paquetes de Java**
>
> Un paquete en Java se utiliza para agrupar clases relacionadas de forma muy similar a una carpeta en un directorio de archivos. Por convención, los nombres de los paquetes se escriben en minúsculas. 

# Formato proyecto

En VSCode usando Maven, crea un proyecto con una estructura predeterminada. Por lo tanto, se debe colocar el código fuente en `src/main/java` y las pruebas en `src/test/java`.

```
.
├── .classpath
├── .project
├── pom.xml
├── .settings
├── target
└── src
    ├── main
    │   └── java
    │       └── App.java
    └── test
        └── java
            └── AppTest.java
```

## Armemos las clases en Java
