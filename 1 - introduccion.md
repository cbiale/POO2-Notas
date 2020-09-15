# Grupo de trabajo

- Adjunto suplente: Claudio Omar Biale

# Libro de Referencia

El libro de referencia es: **Head First Object-Oriented Analysis & Design** de Brett D. McLaughlin, Gary Pollice y Dave West.


![](./figuras/libro1.jpeg)

Este libro cubre los principios y la práctica del diseño orientado a objetos. Son 600 fáciles de leer; los conceptos no son profundos y el libro aborda cada punto desde muchos ángulos.

## Otros libros

Cubriremos temas tratados en los siguientes libros:

- **UML Distilled (3rd edition)** de Fowler, tercera edición: Cubre UML (más algunas facetas del diseño orientado a objetos).
- **Refactoring** de Martin Fowler: Biblia de la técnica de refactorización.
- **Efective Java** de Joshua Bloch: explica tácticas de programación avanzadas en Java, cubriremos algunas en clase.
- **Head First Design Patterns** de Elisabeth Freeman, Eric Freeman, Bert Bates, Kathy Sierra: Este libro cubre los patrones de diseño en profundidad y algunos principios generales de diseño orientado a objetos.
- **Design Patterns** de la banda de los cuatro: La Biblia para patrones de diseño. Desactualizado y más difícil de leer que el libro de referencia.
- **UML @  Classroom: An  Introduction to  Object-Oriented Modeling** de  Martina Seidl,Marion Scholz, Christian Huemer y Gerti Kappel: Excelente libro para abordar el análisis y diseño orientado a objetos.
- **The Elements of UML 2.0 Style** de Scott Ambler: Compendio de guías para UML.
- **Clean Code: A Handbook of Agile Software Craftsmanship** de Robert Martin.
- **UML y Patrones: Introducción al Análisis y Diseño Orientado a Objetos (2da. Edición)** de Craig Larman.
- **Applying UML and Patterns: An Introduction to Object-Oriented Analysis and Designand Iterative Development (3rd Edition)** de Craig Larman.

Durante el transcurso de la materia voy a ir subiendo otros libros de referencia orientados a la programación.

> Erich  Gamma, Richard Helm, Ralph Johnson y John Vlissides conforman la banda de los cuatro.*

# Consideraciones

Las presentaciones o apuntes no reemplazan a la bibliografía de la asignatura.

# Objetivos del Curso

Mejorar su habilidad para:

- Implementar de manera elegante sistemas de software de mayor escala.
- Trabajar eficazmente con un equipo de programadores.
- Pensar de forma independiente e innovadora.
- Comunicar oralmente sus ideas, diseños e implementaciones.


Para dominar temas técnicos y herramientas de ingeniería de software:

- Los componentes del ciclo de vida del desarrollo de software: requisitos, diseño, implementación, prueba y despliegue.
- Metodologías de diseño y codificación, que incluyen diseño orientado a objetos, patrones de diseño, refactorización y UML.
- Herramientas y frameworks de ingeniería de software estándar.
- Conceptos básicos de programación web que incluyen JSON, servidores web RESTful, Javascript.

Otros temas a tratar son:

- Principios de diseño y codificación.
- Refactorización.
- Patrones de diseño.
- Idiomas de programación.

# Proyecto

Seguiremos una línea de tiempo común de seis iteraciones, una cada dos semanas aproximadamente.

La comunicación es un elemento importante de la programación del equipo. 

Habrá sesiones de clase dedicadas al trabajo en equipo.

También habrá presentaciones para darle la oportunidad de describir su proyecto y permitir la crítica de toda la clase.

# Iteraciones

Ciertos hitos deben ser alcanzados por cada iteración. 

Comenzaremos con la codificación en la interacción 3, deben entregar un informe de iteración que describa lo que se logró en comparación con lo que se planeó hacer, y cuales son sus planes para la próxima iteración.

**Iteración 1: Requisitos**: Visión, Lista de características, análisis de dominio, bocetos interfaz gráfica, casos de uso clave *(o historias de usuario)*, arquitectura.

**Iteración 2: Propuesta de Diseño y Prototipos**: El diseño del software para cumplir con los requisitos anteriores ya está formalizado y documentado. Esto incluye una descripción de los componentes principales del software y las interacciones entre ellos. Un prototipo esquelético del diseño propuesto está escrito en código.

**Iteración 3: Primera Iteración de Código Puro**: Se codifica alguna funcionalidad básica, y se pasan al menos algunas pruebas.

**Iteración 4: Trabajo Básico**: La funcionalidad principal del proyecto debe estar funcionando, y hay un buen conjunto de pruebas para ese núcleo.

**Iteración 5: Alfa**: Versión alpha, el proyecto generalmente funciona pero tiene algunos errores y le faltan algunas características deseadas.

**Iteración 6: Proyecto final**: Versión beta, envío de código y demostración del proyecto final.

# Herramientas

Vamos a usar distintas herramientas durante el cursado, algunas son:

- **VSCode**: IDE para desarrollar el proyecto.
- **Java**: Lenguaje usado en POOI, con dicho lenguaje vamos a codificar el servidor.
- **JavaScript**: Lenguaje de programación para el front-end de aplicaciones web.
- **Javalin**: es un framework web liviano para Kotlin y Java compatible con WebSockets, HTTP2 y solicitudes asíncronas.
- **Jackson**: es el mapeador JSON predeterminado para Javalin.
- **Maven**: Herramienta de compilación estándar para proyectos Java.
- **Git**: Software de control de versiones diseñado por Linus Torvalds.
- **PostgreSQL**: base de datos a utilizar en el proyecto.
- **Postman**: desarrollo y test de APIs.
- **Markdown**: lenguaje para documentar.
- **JUnit**: test de software.
- Algo de HTML y CSS.

# Fases del Diseño Ingenieril

Podemos definir **ingeniería de software** como:

> *"La aplicación de un enfoque sistemático, disciplinado y cuantificable para el desarrollo, operación y mantenimiento de software"*.

Existe una metodología de diseño estándar siempre que se desee construir algo Los pasos de la misma son:
- Obtener los requisitos que, por ejemplo, debe cumplir un puente.
- Hacer un diseño completo *(planos, materiales, método de construcción, etc.)*.
- Construir *(implementar)*.
- Realizar pruebas para asegurar de que funcione.

> *En ingeniería de software, este es el modelo clásico en cascada, enfoque inicial a partir del cual evolucionaron otros enfoques.*

# Fases de la Ingeniería de Software Moderna

La ingeniería de software moderna es una variación mucho más flexible de lo anterior.

Deben seguir un esquema como el siguiente:

- Comiencen con un primer paso en los requisitos y el diseño que no estarán completos.
- Implementen las funciones más importantes y obtenga la funcionalidad básica de ejecución.
- A medida que toma forma una implementación inicial, úsenla para refinar los requisitos y el diseño.
- Implementen más funciones, continúen refinando los requisitos y el diseño, y proporcionen versiones continuas de la aplicación en ejecución.

# Escuelas de Desarrollo de Software

Hay muchas escuelas sobre la mejor manera de desarrollar software en equipo.

No vamos a mencionar explícitamente ninguna de las escuelas aquí, pero es posible que *"deseen leer sobre ellas"*: **Lectura 1**.

Vamos a seguir algunos híbridos del agilismo, Extreme Programming (XP) y Scrum.

# Tareas

Instalar los siguientes aplicativos:
- VSCode: https://code.visualstudio.com/download
- Java 14: https://jdk.java.net/14/ o https://adoptopenjdk.net/
- Postman: https://www.postman.com/downloads/
- Git: https://git-scm.com/downloads

Instalar las siguientes extensiones en **VSCode**:
- Java Extension Pack *(vscjava.vscode-java-pack)*
- Project Manager for Java *(vscjava.vscode-java-dependency)*
