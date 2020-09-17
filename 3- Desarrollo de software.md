# Arquitectura cliente servidor

Cliente-servidor es una arquitectura de diseño de software popular que, en un nivel abstracto, divide un software en dos partes: el lado del cliente y el lado del servidor.

- El **lado del cliente** *(o simplemente, el cliente)* es la aplicación que se ejecuta en la computadora del usuario final; proporciona una **interfaz de usuario** que maneja cómo se siente y se ve la aplicación y cómo interactúa con el usuario final. Puede emplear y consumir recursos en la máquina del usuario *(dispositivo informático)*, como almacenamiento temporal y local, etc.

- El **lado del servidor** *(o simplemente, el servidor)* es la aplicación que recibe las solicitudes de los clientes y contiene la lógica para enviar los datos apropiados al cliente. En lugar de una interfaz de usuario, el servidor suele tener una **interfaz de programación de aplicaciones** *(API)*. Además, el servidor a menudo incluye una **base de datos**, que almacenará de forma persistente todos los datos de la aplicación.


Siempre que su aplicación de software se adhiera a la arquitectura cliente-servidor *(es decir, cuando un cliente puede enviar y recibir datos a una API en un servidor)*, puede crear la interfaz de usuario que desee en la plataforma que desee. Esto es ventajoso ya que se espera que las aplicaciones de software modernas estén disponibles en múltiples plataformas y brinden una experiencia consistente en todos los 
dispositivos.

> Una alternativa es usar frameworks que puedan generar código para mobile y web a la vez.

**Veamos un ejemplo concreto**:

Consideremos los pasos principales que suceden cuando queremos acceder al SIU.

1. En primer lugar escribimos la dirección del sitio *(https://ci.fceqyn.unam.edu.ar/autogestion/)* utilizando un navegador web en cualquier dispositivo que ofrezca navegación por Internet.
2. Se muestra una página web en el navegador. Esta página web es la interfaz de usuario del SIU y constituye el lado "cliente" de la aplicación. La aplicación cliente nos permite interactuar con el servidor del SIU *(que  puede ser una computadora física ubicada en una de las sedes de la facultad)*.
3. En el lado del cliente, ingresamos nombre de usuario y contraseña para iniciar sesión en el SIU. En esta etapa, la aplicación cliente *(página web donde se ingresa el nombre de usuario y contraseña)* enviará una solicitud *(de autenticación)* al servidor.
4. La solicitud *(de autenticación)* viaja a través de Internet hasta el servidor del SIU. El servidor, que escucha activamente las solicitudes de todos los usuarios, recibe la solicitud y procede a tratar la solicitud.
5. El servidor realiza una consulta a la base de datos para verificar las credenciales de inicio de sesión. Esta base de datos puede contener información variada, no solamente datos de los usuarios. Se ejecuta la consulta de la base de datos y la base de datos envía los datos obtenidos al servidor.
6. El servidor recibe los datos devueltos por la base de datos y ahora está listo para construir y enviar una respuesta al cliente *(el que solicito ingreso)*. En este caso, la respuesta sería el privilegio de acceder al SIU *(asumiendo que la credencial de inicio de sesión estuviera acreditada)*.
7. La respuesta viaja a través de Internet, de regreso a la computadora. El navegador recibe la respuesta y usa esa información para crear y representar la vista que finalmente veremos después de iniciar sesión correctamente.

# Desarrolle el software que se necesita

> A los ingenieros les gusta resolver problemas. Si no hay problemas fácilmente disponibles, crearán sus propios problemas. **Scott Adams**

¡Antes de inventar un problema, busque uno real! Al considerar una idea para su proyecto, hágase una pregunta sobre la utilidad de su producto. Si está dispuesto a resolver un problema real, disfruta de la ventaja de tener un "cliente" real con "expectativas" reales y un proyecto de software con "requisitos" y "limitaciones" reales.

## ¿Dónde están los problemas "reales"?

Hable con la gente de sus círculos y acepte un problema real que la gente tiene. De hecho, existen muchas aplicaciones de software. Sin embargo, la gente busca constantemente formas mejores, más rápidas y más inteligentes de realizar las tareas diarias. Y afortunadamente para nosotros, los ingenieros de software, todavía hay muchos espacios para mejorar los productos de software existentes *(así como muchos nuevos por construir)*.

# Especificación de requisitos de software

Un requisito es una sola cosa que tiene que hacer el software.

> En la ingeniería de sistemas y la ingeniería de requisitos, los requisitos funcionales definen lo que se supone que debe hacer un sistema y los requisitos no funcionales definen cómo se supone debe ser un sistema. **En POO2, requisito significa requisito funcional**. 

La especificación de requisitos implica definir la funcionalidad prevista del software y las posibles limitaciones de su funcionamiento. 

> Como vimos el primer paso en la construcción del proyecto de software es comprender cuáles son los requisitos. Esta fase también se denomina **Descubrimiento de productos**.


## El documento de especificaciones

En el siguiente enlace tienen disponible un modelo de plantilla para la [**especificación de requisitos del proyecto**](./ejemplos/plantilla_erp.md).

Debemos tener en cuenta que la especificación del sistema de software es uno de los documentos más importantes para conectar al cliente y al equipo de desarrollo *(ingenieros de software)*.

Algunas pautas a tener en cuenta son:
- Cuando se realiza la captura de los requisitos para un sistema de software, deben asegurarse de anotar todos los requisitos *(sin perder ninguna funcionalidad que realmente le interese al cliente)*. Además, deben asegúrarse de que los requisitos sean coherentes entre sí, anotados con precisión y lo más concisos posible.
- Es importante tener en cuenta que una especificación de software es una abstracción de lo que el sistema terminará siendo al final. Cuando comiencen a implementar el sistema y vayan a los detalles de nivel inferior o más bajos, se darán cuenta de que hay problemas con la especificación inicial. Esta bien; de hecho, a menudo hay cosas que no podrían haber descubierto de antemano.

## Mejores prácticas (Recordatorio)

Los proyectos de software que involucran a varias personas comienzan con impresiones muy diferentes sobre cómo debe estructurarse la aplicación. El objetivo principal es expandir y unificar esas visiones en una visión cohesiva.

Esto sucede a través de discusiones, preguntas, bocetos y todas las partes involucradas deben estar en la mesa.

# Wireframe

Además de enumerar las funcionalidades / características deseadas, también necesitamos esbozar cómo interactuará el usuario con nuestro software. Para ese objetivo, normalmente construimos una maqueta o esbozamos un esquema de página o plano de pantalla [*(wireframe)*](https://es.wikipedia.org/wiki/Wireframe_(dise%C3%B1o_web)).

> Existen muchas herramientas gratuitas y propietarias para crear maquetas y/o wireframes. 
> 
> ¡Realmente no van a necesitar un software para esto! Manténgalo simple y usen papel y lápiz, pero siéntanse libres de aprovechar herramientas más poderosas como [Balsamiq](https://balsamiq.com/), [Sketch](https://www.sketch.com/), [Figma](https://www.figma.com/), [InVision](https://www.invisionapp.com/), etc. También pueden encontrar útiles herramientas gratuitas como [mydraft.cc](https://mydraft.cc/), [wireframe.cc](wireframe.cc) o [pencil](https://pencil.evolus.vn/). 

# Modelos de procesos de software

Podemos definir un **proceso de software**  como un conjunto de actividades relacionadas que conducen a la producción de un producto de software. En un nivel abstracto, un proceso de software involucra actividades relacionadas con la *especificación*, *diseño*, *desarrollo*, *validación (pruebas)* y *evolución (mantenimiento)* del software.

Todos los modelos de proceso se pueden clasificar como uno de los siguientes:
- Impulsado por planes *(plan-driven)*
- Ágil

Un proceso **impulsado por un plan** es aquel en el que todas las actividades del proceso se planifican con anticipación y el progreso se mide en función de este plan. Un ejemplo de un proceso impulsado por un plan es el [**modelo en cascada** *(waterfall)*](https://es.wikipedia.org/wiki/Desarrollo_en_cascada).

En cambio, un **proceso ágil** es aquel en el que la planificación es incremental y es más fácil cambiar el proceso de acuerdo con los requisitos cambiantes del cliente.

## ¿Ágil o no ágil?

El proceso de desarrollo ágil de software, desde su creación, produjo una tormenta en la industria del software y rápidamente se convirtió en el estilo de desarrollo más popular y de moda. Hay muchas razones para esto, pero quizás la más importante es que, en la práctica, los equipos de desarrollo que siguieron enfoques basados ​​en planes no pudieron producir sistemas de software de manera rápida y flexible. El proceso impulsado por un plan puede ser engorroso y limitante, ya que los requisitos a menudo cambian y se comprenden de manera imperfecta al comienzo de un proyecto de software.

> El desarrollo de software a menudo se considera un problema perverso, lean la siguiente [reflexión](https://blog.codinghorror.com/development-is-inherently-wicked/)

El proceso de desarrollo ágil, por otro lado, tiene sus raíces en el enfoque de **desarrollo incremental** que implica intercalar las actividades de especificación, desarrollo y validación. El software se desarrolla como una serie de versiones o incrementos, y cada versión agrega funcionalidad a la versión anterior. La idea subyacente en este enfoque es desarrollar una versión inicial de su software, abrirlo a comentarios y luego desarrollar gradualmente versiones más nuevas basadas en estos comentarios.

> Lean este [articulo](https://en.wikipedia.org/wiki/Agile_software_development) como punto de inicio para profundizar sobre este tema.

## ¿Qué es (y no) desarrollo incremental?

La idea de desarrollo iterativo e incremental a menudo se entiende mal. Vean el siguiente [video](https://youtu.be/0P7nCmln7PM) para comprender mejor la metodología ágil.

## Ejemplo de modelo

Se puede seguir un modelo híbrido que se basa principalmente en la metodología ágil *(en particular, en los métodos de desarrollo ágiles de Extreme Programming (XP) y Scrum)*.

El proyecto se divide en varias iteraciones :

- Comiencen con un primer paso en donde los requisitos y el diseño no estarán completos.
- Implementen las funciones más importantes y hagan una aplicación que ejecute las funciones básicas.
- A medida que toma forma una implementación inicial, úsenla para perfeccionar los requisitos y el diseño.
- Implementen más funciones, continúen perfeccionando más los requisitos y el diseño, y proporcionen versiones continuas de la aplicación en ejecución.

> Comparen esto con las iteraciones descriptas en la clase anterior.

> **¿Con cual consideran van a trabajar mejor?**
