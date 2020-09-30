# Programación orientada a Objetos

 Enseñar programación orientada a objetos *(POO)* a quienes no tienen experiencia en programación es más fácil que a quienes tienen experiencia en programación *(procedimental o funcional)*. 
 
 Esto se debe a que los programadores experimentados se acostumbran al pensamiento y modelado procedimental *(o funcional)*. 
 
 
 Por otro lado, para los no programadores, la forma orientada a objetos de descomponer un problema es similar a la forma en que se utilizan para ver situaciones de la vida real. De hecho, vivimos en un mundo formado por objetos que interactúan.

> Key A., "Microelectronics and Personal Computer." Scientific American 237(3):230-244 (1977)

## Objeto
 
"Un objeto representa un elemento, item, unidad o entidad individual e identificable, ya sea real o abstracta, con un papel bien definido en el dominio del problema"

> Smith, M., and Tockey S. "An Integrated Approach to Software Requirement Definition Using Objects." Boeing Commercial Airplane Support Division, Seatle, WA, (1988).

En un lenguaje de programación orientado a objetos basado en **clases**, como Java, cualquier objeto debe ser una instancia de una clase.

## Clase 
Una clase define los atributos, la estructura y las operaciones que son comunes a un conjunto de objetos, incluida la forma en que se crean los objetos.

Una clase es una **abstracción** o un modelo.

## ¿Qué es un modelo?

Un modelo es una representación parcial de otra cosa *(un concepto, un sistema, un patrón, etc.)*. Nos ayuda a visualizar y comprender el original y su función en el dominio de un problema.

Cuando modelamos algo *(es decir, creamos una abstracción de él)*, nos enfocamos en algunas de sus características *(que son importantes para el problema en cuestión)* e ignoramos otras *(que se consideran irrelevantes para resolver el problema)*.

## Un objeto tiene estado y comportamiento.

El estado de un objeto *(también conocido como sus propiedades o atributos)* son sus características esenciales y distintivas. Una clase declara atributos de sus objetos a través de sus campos de datos *(variables o atributos de instancia)*. El estado de un objeto es el valor de esos campos de datos en cualquier momento.

El comportamiento de un objeto es el conjunto de operaciones o responsabilidades que debe cumplir. Esto incluye la responsabilidad de proporcionar y modificar información de estado cuando los clientes lo soliciten *(otros objetos o servicios)*. El comportamiento de un objeto se define mediante el método de instancia que implementa ese comportamiento. Invocar un método en un objeto es pedirle al objeto que cumpla un comportamiento *(que realice una acción)*.

## Encapsulación

Un lavarropa es un objeto. Suceden muchas cosas dentro de un lavarropa, pero se interactúa con él a través de ciertas operaciones establecidas. Por ejemplo, se puede configurar la temperatura de lavado, el tipo de lavado, la velocidad de secado y en cada caso, cambiar su estado. Cómo funciona exactamente un lavarropa no es de su incumbencia. Un lavarropa es, en cierto sentido, una caja negra para la persona que lo usa.

Los objetos, tanto en el software como en la vida real, se construyen de manera que encapsulan su estado y comportamiento en una unidad *(un paquete, una cápsula, una caja negra, etc.)* con una interfaz para permitir y simplificar el acceso a el usuario.

La clase es una unidad de encapsulación en POO; proporciona la maquinaria para agrupar el estado y el comportamiento *(campos de datos y métodos que funcionan con esos datos)* dentro de una unidad. El estado suele ser privado para el objeto y no *(directamente)* visible para los clientes. Este concepto de negar el acceso directo al estado de un objeto se denomina **ocultación de información**. Además del estado, algunos de los comportamientos *(responsabilidades)* de un objeto también pueden estar ocultos y solo utilizados por el objeto. El conjunto de comportamiento visible *(público)* de un objeto forma su **interfaz** y define cómo colabora *(actúa y reacciona)* con otros objetos.

## Herencia y polimorfismo

Puede existir una relación de superclase/subclase entre dos clases cuando una clase *"es una especie o tipo de"* la otra clase. Las subclases heredan la estructura y el comportamiento de su superclase. Por lo tanto, el comportamiento y los atributos comunes se pueden definir solamente en la superclase en lugar de repetirse en cada subclase.

El polimorfismo *(que tiene muchas formas)* es la capacidad de una entidad en un modelo orientado a objetos para referirse a objetos de diferentes clases en diferentes momentos. Por ejemplo, un método que acepta un objeto de cierta clase también operará en sus subclases.

## Composición de objetos

Otra forma eficaz de reutilizar código *(pero sin herencia)* es mediante la composición de objetos que, en pocas palabras, es una forma de combinar objetos en otros más complejos.

# Análisis y diseño orientado a objetos

El análisis y diseño orientado a objetos es un enfoque de ingeniería de software que modela un sistema como un grupo de objetos que interactúan.

Los objetos deben modelar el comportamiento y el estado relevante para el sistema que se está implementando. Solo ciertas propiedades y comportamientos son relevantes; identificar lo que es relevante es una parte clave del análisis y diseño orientado a objetos.

Implica: 
- **Análisis**, o modelado de problemas, en el que se describe y representa el problema.
- **Diseño**, o modelado de soluciones, en el que se descubre y representa una solución al problema.
- **Implementación**, en la que se escribe y prueba el código que conforma el sistema que se encuentra desarrollando.

En un modelo tradicional basado en planes *(como "Cascada")*, estos pasos se toman en orden y por turno. En un modelo de desarrollo de software ágil, se toma el enfoque incremental para el desarrollo donde en cada ciclo *(iteración)*, se analiza un poco, se diseña un poco y luego se codifica un poco. Al final del ciclo, recibe comentarios y se responde a los cambios.

El ciclo de analizar un poco, diseñar un poco, codificar un poco es lo que se espera empleen a través de las iteraciones del proyecto.

