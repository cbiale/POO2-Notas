# Historias de usuario

Una de las formas más utilizadas de capturar requisitos en un formato útil para ingenieros y clientes son las historias de usuario. 

Las historias de usuario son documentos breves y concretos que capturan para quién es una característica, cuál es su valor y cuánto tiempo llevará construirla.

Las historias de usuario están escritas en un formato llamado **rol-objetivo-beneficio**:

```
Como <tipo de usuario>, quiero <alguna meta u objetivo> para <beneficio/valor>
```
Este formato obliga al cliente y al desarrollador a pensar realmente en quién se beneficiará de una función, qué están tratando de lograr y por qué quieren lograrlo. 

Al capturar una característica *(requisito funcional)* de una manera tan concreta, les brinda a todos la oportunidad de pensar realmente si una característica realmente vale la pena o no y si agrega un valor concreto real a un producto.

> **Sugerencia**
>
> Cuando pensamos en historias de usuarios, es importante no sentirse demasiado limitado por el proceso. 
>
> Un lugar en el que la gente encuentra esto limitante es en términos de rol-objetivo-beneficio.
> 
> El papel de nuestras historias de usuario no siempre tiene que ser el de entidades humanas.
>
> También pueden ser sistemas de back-end, servidores de terceros y otros sistemas.

## Lista de verificación *(checklist)* de historias de usuario

Hacer que las historias de los usuarios sean correctas suele ser un desafío, especialmente cuando recién comenzamos con esto.

Aquí hay un conjunto de pautas para ayudarlo a escribir historias de usuarios efectivas:

- Que sean breves, simples e independientes entre sí.
- Escriban desde la perspectiva del usuario.
- Aclaren el valor/beneficio de la historia: ¿cuál es el motivo de la historia?
- Describan una pieza de funcionalidad. Si es necesario, divídanlas en más historias.
- Escriban historias en equipo.

## Ejemplos

Tomando como referencias del proyecto que estamos desarrollando podemos tener las siguientes historias de usuario:

Debe tener:
- Como estudiante, quiero agregar un curso para poder escribir una reseña sobre el mismo.
- Como estudiante, quiero calificar un curso dándole un valor de 0 a 10 para poder cuantificar mi experiencia general al tomarlo.
- Como estudiante, quiero escribir un comentario abierto sobre un curso que he tomado para poder desarrollar la calificación que proporcioné.
- Como estudiante, quiero buscar un un curso para poder darle una revisión o leer todas sus revisiones.
- Como estudiante, quiero examinar todas las reseñas de un curso para poder aprender más sobre un curso que estoy considerando tomar.

Es bueno tener:
- Como estudiante, quiero ver una calificación promedio de un curso para poder tener una impresión general de lo que otros experimentaron al tomar el curso.
- Como estudiante, quiero que me guste / no me guste una reseña para poder estar de acuerdo o en desacuerdo con un reseñador.
- Como estudiante, quiero ordenar las reseñas basado en varios criterios para poder encontrar fácilmente la información más relevante que busco.
- Como estudiante, quiero ordenar marcar una reseña como inapropiada para que el administración pueda eliminarla de las reseñas.
- Como administrador, quiero poder eliminar una reseña si se considera inapropiada para que la aplicación no se convierta en un lugar para los trolls.


Las historias de usuario se puede documentar usando el siguiente formato:
- Id
- Título
- Prioridad
- Tiempo estimado 
- Historia de usuario

# Backlog del proyecto

El Backlog del proyecto *( Backlog del Producto)* es la lista actual de historias de usuarios para el Proyecto. Las historias de usuarios deben organizarse en grupos *(por ejemplo, "Debe tener", "Es bueno tenerlas", "Fuera del alcance", etc.)* y priorizarse.

Asignen mayor prioridad a las historias de usuario que tienen el mayor impacto y se pueden hacer más fácilmente *([regla 80/20](https://es.wikipedia.org/wiki/Principio_de_Pareto))*. Las historias de usuario se pueden agregar, modificar o eliminar del Backlog durante el desarrollo del proyecto.

## Backlog de iteración

Antes de iniciar una iteración, debe seleccionar un subconjunto de historias de usuario del Backlog del proyecto que se planea entregar durante la iteración. Puede dividir aún más cada historia de usuario en tareas. Las tareas son las actividades realizadas para entregar una historia de usuario.

# Estimación y planificación

Como desarrollador de software, ustedes también estarán en condiciones de estimar el costo y el tiempo para desarrollar un software.

La estimación de un proyecto es la suma de las estimaciones de sus historias de usuarios.

Deben agregar una estimación a cada historia de usuario del tiempo que creen que llevará desarrollar *(es decir, diseñar, codificar, probar y entregar)* esa funcionalidad.

Se debe considerar que es difícil estimar el tiempo que llevará desarrollar una historia de usuario. Como alguien que está comenzando con esto, puede parecer imposible hacerlo bien. Esto es difícil *(y propenso a errores)* incluso para desarrolladores experimentados debido a un fenómeno conocido como la [falacia de la planificación](https://es.wikipedia.org/wiki/Falacia_de_la_planificaci%C3%B3n).

En el desarrollo de software ágil, los profesionales combaten la falacia de la planificación al:

- Obtener estimaciones de varias personas.
- Estimar el "esfuerzo requerido" en términos de "días ideales" o "Puntos de historia".
- Usar estimaciones relativas *(por ejemplo: esta funcionalidad requiere el doble del esfuerzo que dedicamos a tal funcionalidad)*.

## Precaución

Si las estimaciones de historias mayores a 13 *(días ideales)* no pueden caber en una iteración. Es posible que deseen intentar dividir esa historia en varias historias más pequeñas y más fáciles de estimar.

Si la estimación total de todas las historias de usuario en la categoría **debe tener** es mucho mayor que la duración de cinco iteraciones, deben realizar cambios *(incluso la eliminación del proyecto en favor de uno más pequeño)*.

## Día ideal

Una unidad para estimar el tamaño de los items del backlog del producto según el tiempo que tardaría en completarse un item si fuera el único trabajo que se realiza, que no hubo interrupciones y todos los recursos necesarios para completar el trabajo están disponibles de inmediato.

> Al estimar, se debe tener en cuenta el tiempo que se dedicará a investigar o aprender sobre el desarrollo de una funcionalidad.

## Puntos de historia 

Utilizado por los ingenieros de software con más experiencia. Se estima el esfuerzo requerido como una combinación de la complejidad del trabajo, el riesgo y la incertidumbre involucrados en él. 

> Para complementar lean [Puntos de historia y estimación](https://www.atlassian.com/es/agile/project-management/estimation)