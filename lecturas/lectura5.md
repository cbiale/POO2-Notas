# Lectura 5 - Tipos de diagramas

## Visión General

UML es un estándar de diagramación para diagramas para ayudar al proceso de diseño.

> Una imagen vale más que 1000 palabras.
> Un lenguaje de imágenes común ayuda al igual que un lenguaje verbal común *(español, inglés, etc.)*.

UML facilita enormemente el diseño orientado a objetos/centrado en la arquitectura, todos los diagramas, excepto dos, se centran en la estructura de objetos/componentes.

Hay diferentes tipos de diagramas, algunos más y otros menos críticos. Clases de diagramas UML:
- **Diagramas estáticos**: sin componente temporal. La mayoría muestra clases/objetos y cómo se relacionan.
- **Diagramas dinámicos**: muestran cómo los objetos interactúan en el tiempo.

## Perspectivas diferentes para utilizar diagramas

Los diagramas UML se pueden usar en todos los niveles de diseño, y su uso es sutilmente diferente en cada nivel:

- **Conceptual** *(parte de la captura de requisitos)*: Para comprender el dominio subyacente; No es necesario pensar en la relación con el software resultante. Los modelos de dominio son un modelo conceptual. Los modelos conceptuales son un buen lugar para comenzar a diseñar.

- **Especificación** *(parte del diseño inicial)*: Mirando las entidades en los diagramas como especificaciones de lo que debe hacer el código *(interfaces)*, no el código real *(implementación)*. Muy a menudo, la perspectiva que se desea utilizar.

- **Implementación** *(parte de la codificación)*: La implementación real. Para diagramar implementaciones de manera efectiva, debe centrarse en las operaciones/atributos clave o las imágenes se vuelven demasiado grandes.

## Diagramas de Clase

> Capítulos 3 y 5 del libro de Fowler, Capítulo 4 de UML@Classroom.

Los diagramas de clase son el tipo más útil de diagrama UML. Eviten hacer diagramas que contengan demasiada información.

Que omitir:
- Omitir atributos y asociaciones no críticos.
- Hacer diagramas enfocados para un caso de uso dado: hacer un diagrama de clase que solo muestre las clases relevantes para el caso de uso *(o historia de usuario)*.
- No muestre clases que no sean centrales para el diseño, por ejemplo, String, HashSet, etc.
- No coloque anotaciones relacionadas con la implementación demasiado pronto *(navegabilidad, público/privado, tipos)*.
- Ponga todo lo que importa para el problema que está resolviendo con el diagrama, y ​​nada más.

Solo los roles importante necesitan ser explícitos. Si no hay un nombre en un extremo, el nombre de la clase en ese extremo es el nombre implícito del rol. Si existe una asociación, no es necesario mostrar el atributo que representa a dicha asociación en la clase.

Las interfaces se diagraman como clases con la especificación << Interfaz >>. Una interfaz usa la misma flecha que la generalización, pero la línea es punteada.
 
> << ... >> es un estereotipo: significa que estamos usando la notación UML para algo que es similar, pero diferente, de lo que originalmente estaba destinado.

Para indicar que una clase es abstracta, se debe agregar la restricción {abstract}.

La agregación es una asociación todo-parte. Se coloca un diamante en el extremo "todo" de la asociación. Si el diamante es pintado, es además una composición: las partes son componentes integrales del todo, y cuando el todo muere, las partes también mueren.

> Puede ser difícil distinguir la agregación de la composición; no se preocupen demasiado por eso.

## Diagramas de Casos de Uso

> Capítulo 9 del libro de Fowler, Capítulo 3 de UML@Classroom.

Los diagramas de casos de uso son útiles desde el principio: aclaran quién estará involucrado en cada caso de uso. Si no hay muchos actores distintos involucrados en una aplicación, los diagramas de casos de uso no son muy útiles.


## Diagramas de Secuencia

> Capítulo 4 del libro de Fowler, Capítulo 6 de UML@Classroom.

Los diagramas de secuencia permiten mostrar actividades dinámicas, a diferencia de los diagramas de clases que permiten mostrar actividades estáticas. Son particularmente buenos en la fase de diseño para aclarar dudas en los casos de uso: dibuje un diagrama de secuencia para el caso de uso.

## Diagramas de Actividad

> Capítulo 11 del libro de Fowler, Capítulo 7 de UML@Classroom..

El único diagrama UML que no está fuertemente basado en objetos. Permiten mostrar actividades dinámicas. Diseñado para mostrar actividades sin asignarlas a objetos todavía Útil para la especificación temprana de casos de uso, en la parte de requisitos.


## Diagramas de Paquetes, Componentes y Despliegue

> Capítulo 7, 8 y 14 del libro de Fowler.

Los diagramas de paquetes son variaciones simples de los diagramas de clase para mostrar los paquetes y sus relaciones.

Los diagramas de componentes se utilizan en grandes piezas de software para mostrar los componentes y cómo están relacionados.

Los diagramas de despliegue son para sistemas distribuidos permiten mostrar los diferentes nodos y cómo están conectados.

Ninguno de estos diagramas es muy útil para aplicaciones con solo 1-2 paquetes/componentes/nodos de implementación.

## Diagramas de Objetos

> Capítulo 6 del libro de Fowler.

Estos diagramas son muy simples, solo muestran una instantánea de los objetos en tiempo de ejecución.

## Diagramas de Comunicación

> Capítulo 12 del libro de Fowler, Capítulo 6 de UML@Classroom.

Permiten mostrar actividades dinámicas. Los diagramas de secuencia son generalmente los mejores para mostrar interacciones centradas en objetos. En algunos casos, los diagramas de comunicación también pueden ser útiles. Los diagramas de comunicación también muestran la interrelación estática de los objetos, pero no ilustran el aspecto temporal que si se ven en los diagramas de secuencia.

## Diagramas de Máquina de Estado

> Capítulo 10 del libro de Fowler, Capítulo 5 de UML@Classroom.

Los diagramas de Máquina de estado son simplemente autómatas finitos elegantes: cada nodo tiene un estado diferente y las aristas indican transiciones dinámicas de estado a estado. La estructura de estados puede ser una dimensión importante de algunos diseños.

Considere los estados en los que pueden estar las clases 
*(Por ejemplo, una factura se encuentra en uno de los siguientes estados: recién creada, pendiente, programada, vencida, cerrada)*.

Una señal de que un objeto tiene estado: algunos mensajes solo funcionan parte del tiempo *(solo en ciertos estados)*.

Algunos sistemas no tienen clases interesantes con estado. No se concentre en la estructura del estado si solo hay dos estados. Pero, reconocerlos cuando existen es crítico, y un diagramas de Máquina de estado será útil.

## Modelando Sistemas IT

Se pueden encontrar cuatro puntos de vista diferentes, cada uno de los cuales enfatiza ciertos aspectos y que están estrechamente relacionados entre sí.

- **Vista Externa**: diagrama de caso de uso y diagrama de secuencia de casos de uso *(Diagrama de secuencia de sistema)*.
- **Vista Estructural**: diagrama de clases.
- **Vista de Interacción**: diagrama de secuencia y diagrama de comunicación.
- **Vista de Comportamiento**: diagrama de estado.
