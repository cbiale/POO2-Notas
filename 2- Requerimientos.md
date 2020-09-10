# Recopilación de requisitos 

**Descubrimiento de producto**: Paso uno en la *creación de software*: entender cuáles son los requisitos. Esta fase también se llama *descubrimiento de producto*.

Los proyectos de software involucran a **n personas** y comienzan con **n** impresiones muy diferentes sobre cómo debe estructurarse la aplicación.

El objetivo principal en esta etapa es expandir y unificar esas **n visiones** en una única **visión coherente**.

Esto sucede a través de extensas discusiones, reuniones, preguntas y bocetos.

Todas las partes involucradas deben estar en la mesa: 
- gerencia, 
- desarrolladores, 
- clientes.


> Para su proyecto, es posible, que deseen comenzar con varias ideas y trabajar un poco en cada una y elegir una ganadora.


# Componentes

Los componente a desarrollar son:
- **Declaración de visión**: uno o dos párrafos sobre la visión compartida de clientes y desarrolladores sobre lo que debe hacer la aplicación.
- **Lista de características**: sí, una lista con viñetas de características que la aplicación debería tener.
- **Bocetos de interfaces de usuario** y cómo se usan.
- **Algunos casos de uso**: para procesos involucrados, una secuencia paso a paso de cómo debe desarrollarse un escenario particular de interacción usuario-aplicación.
- Posibles bibliotecas o frameworks que se van a utilizar.

# Otros objetivos

Identificar las diferentes partes potenciales *(actores)* que interactuarán con el sistema y enfocarse en sus necesidades al reunir los requisitos.

Realizar un **Análisis de dominio** donde se busca comprender mejor el dominio subyacente de la aplicación *(por ejemplo, formatos de archivos de música y reglas de copyright para una aplicación de transmisión de música)*.

Explorar diferentes marcos y bibliotecas que podrían usarse, y establezca un plan inicial.

# Otros temas a tener en cuenta

Debemos indagar sobre:
- ¿Cuál es el mercado para la aplicación? ¿Quién lo usará realmente?
- ¿Cuál es la viabilidad de codificarlo en el plazo disponible? ¿Se puede dividir lógicamente entre el equipo?
- Mirar a la competencia: ¿existen aplicaciones similares?
- ¿Cuál es la estructura organizativa del equipo? ¿Líder fuerte, colección de líderes, o altamente democrático?


# Listas de características

Se deben enumerar las características que debe tener la aplicación *(por ejemplo "Soporte de inicio de sesión de Facebook", etc.)*.

Las **funciones principales** son las más básicas, y las **funciones extendidas** son objetivos a largo plazo.

# Casos de uso


Los casos de uso *(también llamados historias)* son secuencias de eventos que representan comportamientos que el sistema en funcionamiento debería tener.

Los casos de uso son útiles para desarrollar una aplicación.

El proceso de escribir casos de uso expondrá detalles de la funcionalidad esperada.

Se puede elaborar y ampliar progresivamente *(o reducir y eliminar)* los casos de uso hasta que sean lo suficientemente estables y sensibles como para implementarlos.

Se puede usar los casos de uso para ayudar a comenzar con la codificación.

Aquí, en los requisitos, estamos *"centrados en el cliente"*, es decir sobre cómo se utilizará el sistema.

Luego se ​​evoluciona en el diseño para estar *"centrados en el código"*, un bosquejo de un algoritmo.

# Encontrar los casos de uso correctos

Use las listas de características, los bocetos de la GUI, etc. como paso para obtener casos de uso.

Concéntrese en los casos con un número no trivial de pasos, los cortos no necesitan ser escritos.

Del mismo modo, si un boceto o guión gráfico de la interfaz de usuario muestra claramente la secuencia de eventos, no hay necesidad de duplicar eso en un caso de uso.

# Lista de características vs Casos de uso

La lista de características son descripciones de características en una sola oración.

Los casos de uso son descripciones paso a paso del comportamiento del sistema.

### Ejemplo:

- Una característica de una aplicación de pago de libros de la biblioteca podría ser simplemente *"La capacidad de cobrar recargos por libros atrasados"*.

- Un caso de uso de la misma aplicación podría ser *"devolver el libro y calcular el recargo por pago atrasado"*, un escenario paso a paso puede ser:

	1. un usuario devuelve un libro físico,
	2. el libro es escaneado,
	3. se marca como devuelto en la base de datos, y
	4. un recargo por retraso, si lo hubiera, se calcula y agrega a la cuenta del usuario.


# Formato para escribir casos de uso

Incluir siempre un título descriptivo.

El cuerpo es la ruta principal del caso de uso, una lista numerada de acciones 1. 2. 3. .. donde se describe lo que se realiza.

Rutas alternativas opcionales del caso de uso: donde se especifican otras formas en que el caso de uso podría proceder.

Opcionalmente, se puede incluir una ruta opcional si existen algunos pasos que se pueden omitir.

No se necesita usar rutas alternativas u opcionales, inclúyalas solo si ofrecen una especificación más clara que hacer casos de uso separados.

# Bocetos de la intefaz de usuario

No tienen que hacerlos bonitos, pero ayuda a que la aplicación se sienta real si se le dedica algo de tiempo a trabajar en esto.

Deben revisar cuidadosamente las listas de características y los casos de uso para asegurarse de cubrir las listas de características y casos de usos con los bocetos.

Existen herramientas de creación de prototipos y guiones gráficos de la interfaz de usuario que permiten secuenciar un camino a través de las diferentes interfaces de usuario, esto puede ser de gran ayuda.

# Propuesta de arquitectura inicial

Es una propuesta inicial para las arquitecturas de software, frameworks, etc. y cómo se van a implementar.

Se puede enumerar cada componente que se necesite.

Por ejemplo, si la aplicación incluye reconocimiento facial en imágenes y se desea utilizar alguna biblioteca de terceros para hacer eso, se debe enumerar dicha biblioteca.

# Análisis de dominio

Debe comprender a fondo el dominio de su aplicación antes de comenzar a diseñarla.

El análisis de dominio es cualquier actividad que aumenta la comprensión del dominio subyacente sobre el que va a trabajar el software.

### Ejemplo:

- En un restaurante *(incluso sin una computadora)* el *"dominio"* es el restaurante real con entidades que incluyen pedidos, elementos de menú, mesas, pagos, recibos, etc.

- Si está creando una aplicación de red social, ¿qué grupos de relaciones están permitidos? ¿Amigos? ¿Familia? ¿Amigos de amigos? ¿Y quién puede ver lo que hay en cada grupo?


Se debe pensar en este tema y escribir al menos algo para la iteración 1; dependiendo del dominio puede ser poco o mucho.


# Captura de Requisitos Iterativos

Deben hacer varias rondas para realizar las listas de características / casos de uso / bocetos de la interfaz de usuario.

Usen cada una para ayudar a refinar y expandir las mismas.

Tienen dos oportunidades en el camino a desarrollar: la Iteración 1 e Iteración 2.




