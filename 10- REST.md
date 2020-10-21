# Separación de cliente y servidor

Hemos establecido que nuestro interés radica en soluciones de software que se ajusten a la arquitectura **Cliente-Servidor**.

Una práctica común para separar el cliente y el servidor es el estilo de arquitectura REST *(Representational State Transfer)*. En este estilo, la implementación del cliente y el servidor se realiza de forma independiente sin que cada uno sepa sobre el otro. Esto significa que el código del lado cliente / servidor se puede cambiar en cualquier momento sin afectar al otro lado.

> **RESTful**
> 
> Sistemas compatibles con REST, a menudo denominados sistemas **RESTful**.

> **REST es sin estado**
> 
> Una característica importante de los sistemas RESTful es que son sin estado. En la arquitectura Cliente-Servidor, sin estado significa que el servidor no necesita saber nada sobre el estado en el que se encuentra el cliente y viceversa.

Entonces, ¿cómo colaboran *(se comunican)* cliente y servidor? Lo hacen enviándose **"mensajes"** entre ellos. El cliente envía un mensaje de solicitud y el servidor responde con un mensaje de respuesta. Cada mensaje de solicitud enviado por el cliente debe ser autónomo: la ausencia de estado de REST significa que el servidor y el cliente deben comprender cualquier mensaje recibido, sin ver los mensajes anteriores. Para obtener más información lean sobre [REST](https://en.wikipedia.org/wiki/Representational_state_transfer).

# Comunicación entre cliente y servidor

Siempre que cada parte sepa qué formato de mensajes enviar a la otra, pueden comunicarse entre sí. Los mensajes enviados generalmente se clasifican en mensajes de **solicitud** y **respuesta**. Y el protocolo de comunicación más común es **HTTP**.

## ¿Qué es HTTP? #

HTTP significa Hypertext Transfer Protocol *(Protocolo de transferencia de hipertexto)* y se utiliza para estructurar solicitudes y respuestas a través de Internet.

Hay 4 verbos *(operaciones o métodos)* HTTP básicos que usamos en las solicitudes para interactuar con el servidor:
- **GET**: recupera un recurso específico *(por id)* o una colección de recursos.
- **POST**: crea un nuevo recurso.
- **PUT**: actualiza un recurso específico *(por id)*.
- **DELETE** - eliminar un recurso específico *(por id)*.

> Existen otros [verbos](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol#Request_methods)

Una solicitud HTTP, además de un verbo HTTP, normalmente consta de:
- un encabezado, que permite al cliente pasar información sobre la solicitud.
- un camino a un recurso.
- un cuerpo de mensaje opcional que contiene datos.

> Para poder enviar una solicitud a un servidor http dado se abre un socket de red para una dirección y puerto determinado. 

El servidor luego de tratar una solicitud devuelve una respuesta que incluye:
- Información del encabezado, incluido el código de estado.
    - 200 OK es el código HTTP que indica que todo ha salido bien.
    - 4XX para varios tipos de error.
    - Existen muchos otros, para ello vean el siguiente [enlace](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes).
  - Un cuerpo arbitrario: puede ser el código html de una página web, datos en formato JSON para una respuesta RESTful del servidor, un binario de imagen .jpg, etc.

# ¿Qué es la API RESTful? #

La interfaz de programa de aplicación *(API, Application Program Interface)* permite la interacción entre dos sistemas. Una API RESTful es una API que se ajusta al estilo REST y establece qué funcionalidades proporciona el servidor al cliente y cómo las proporciona.

## Servicios Web

La mayoría de las aplicaciones modernas de celular y web tienen un servicio RESTful en  segundo  plano que  controla toda  la  lógica empresarial subyacente: son  los"cerebros".

> **Un ejemplo de servidor RESTful básico**
>
> Un servicio web de carrito de compras que permite agregar un artículo al carrito, enumerar contenidos, eliminar un artículo, pagar, etc.

Un servicio web RESTful se ejecuta sobre el protocolo web http(s) estándar. Pero utiliza http como una  interfaz arbitraria: envía solicitudes arbitrarias *(no solo solicitudes de página web html/css/images)* y devuelve resultados arbitrarios *(no solo html/css/etc.)*. 

> La clave para un buen protocolo RESTful es una especificación clara de las solicitudes permitidas y las respuestas esperadas.

> Un servidor web/servidor RESTful no es más que un proceso que escucha repetidamente las conexiones en un puerto TCP/IP *(generalmente 80 para http y 443 para https)*.
> 
> Un navegador/cliente RESTful abre conexiones y envía solicitudes.

# ¿Qué es un punto final de API?

HTTP requiere que los datos se transfieran de un punto a otro a través de la red. Un punto final de API es el punto de entrada en un canal de comunicación cuando el cliente y el servidor interactúan.

## Recurso, ruta y punto final

Un punto final es un elemento de datos particular al que REST debe acceder *(por ejemplo, cursos)*.

Una ruta es un sufijo de URL para acceder al recurso necesario *(por ejemplo/cursos/5 para hacer referencia al curso con identificador 5)*.

Un punto final es una ruta más un método HTTP *(GET/PUT/DELETE/...)*.

> Para ser 100% claros sobre el formato de solicitud/respuesta de los puntos finales admitidos por nuestra API, necesitamos escribir una especificación precisa *(documentar la API)*.

> **Información adicional**
> 
> Para tener una descripción general práctica de http *(y sus métodos)* y REST, pueden mirar este [video](https://www.youtube.com/watch?v=iYM2zFP3Zn0) y este [otro](https://www.youtube.com/watch?v=Q-BpqyOT3a8). Sin embargo, tengan en cuenta que algunos de los contenidos tratados están fuera del alcance de nuestra clase.

# Framework Web 

**Javalin** es una biblioteca Java para desarrollar servidores web. Abstrae los aspectos de bajo nivel de la comunicación entre el servidor y el cliente al tiempo que evita las ser complejo en cuanto a su funcionamiento, por ello es apto para iniciarse en el desarrollo web. 

Para devolver resultados del servidor usaremos **Jackson**, una biblioteca de Java que permite mapear las estructuras de datos de Java a JSON y viceversa. Jackson es el mapeador JSON predeterminado para Javalin.

> Inspirado por Sinatra *(Ruby)* e incluso similar a Flask *(Python)*. Es un derivado de Spark-Java.

# JSON

El servidor y el cliente se comunican con un protocolo basado en texto sin formato *(HTTP)*. Pero necesitan intercambiar datos que estén más estructurados que el texto sin formato, por ejemplo, objetos, listas, etc.

Un formato de intercambio de datos es una convención sobre cómo formatear datos estructurados en texto sin formato. JSON es un estándar de la industria, es más simple y más liviano que otras alternativas populares (por ejemplo: XML). 

# Entorno de Desarrollo de API

Una API *(Application Programming Interface)* establece qué funcionalidades proporciona el servidor al cliente y cómo las proporciona.

Una vez que se diseña la API, diferentes personas pueden trabajar en el servidor y en el cliente de forma independiente, incluso en paralelo, mientras ambas partes sigan la API, la aplicación funcionará al final.

Un **ADE (API Development Environment)** es  de  ayuda para  diseñar la  API, documentarla, probarla, interactuar con ella, etc. En la materia usaremos **Postman**. 

> Existen alternativas como Insomnia, SoapUI, Karate, etc.

# Servidor RESTful

Las solicitudes RESTful ingresan al servidor web y deben enviarse/enrutarse al código Java para ejecutarse, ¿cómo lo hacemos?. 

Respuesta: usamos un framework de servidores RESTful como **Javalin**.

Javalin o SparkJava son parte de una nueva tendencia de **Microservicios** para usar pequeños servidores RESTful para cada tarea distinta. Los  microservidores son  mucho  más  simples que  los  viejos frameworks pesados *(Spring, Tomcat, Django, Rails, etc.)*. 

Javalin es solo un paquete Java, por lo que no es necesario instalar nada, solo se debe agregar la dependencia Maven. Cuando ejecuten la aplicación que usa Javalin, iniciará automáticamente un servidor web **Jetty** basado en Java.

## Ejemplo de Distribución de Clases

**Servidor**: la clase principal que configura la base de datos y los puntos finales.

**Curso**: una clase del "modelo", representa un curso.

**CursosControlador**: se  encarga  de  manejar las  entradas, esta  clase contiene el código que maneja las diferentes rutas/puntos finales.

**CursosRepositorio**: front-end de la base de datos, implementa agregar/eliminar/etc.

**El método .routes (..)** del Servidor toma una función como parámetro que configura todas las rutas.

Observe que las rutas/puntos finales http están aislados de las clases **CursosXX**, y cómo la base de datos está aislada de todas las clases excepto **CursosRepositorio** => **separación de preocupaciones**.

## El Modelo en el servidor

El núcleo del servidor son objetos Java normales *(POJO's, Plain Old Java Objects)* que nos permiten modelar el dominio en cuestión. 

El código del  modelo no  debería  preocuparse por  los  datos persistentes o  por  crear JSON para el navegador, todo ello con el objetivo de mantener una clara **separación de preocupaciones**.

La clase **Curso** es la única clase de modelo en este ejemplo simple. En una aplicación más grande habrá muchas clases de este tipo *(piensen en las otras clases del problema tratado en clases anteriores)*. Cualquier operación subyacente sobre los  datos deben ser  métodos en  las clases del modelo.

## La Capa de persistencia

Este término se refiere a la base de datos en el back-end: casi todos los servicios web sirven datos persistentes de algún tipo de base de datos.Dado que los datos están en una base de datos en un dispositivo de almacenamiento, el servidor puede caer y los datos no perderse *(evitando la perdida de datos)*.

## JSON ↔ Objeto Java ↔ Base de Datos

Existen tres representaciones diferentes de los mismos datos que deben conectarse. Esto es un problema clásico en aplicaciones web y telefónicas. Para dividir y  solucionar este  problema, es posible hacer dos  asignaciones independientes:
- JSON ↔ objeto Java 
- Objeto Java ↔ fila en la base de datos

Es posible simplificar estos pasos, pero recuerden: **separar las preocupaciones correctamente conduce a un código más robusto**.

**JSON ↔ Objeto Java**

Asigne cada campo JSON a un campo *(atributo)* de un objeto Java. Jackson  puede asignar  automáticamente un campo JSON a campo Java en  ambas direcciones.

> En un POST podemos usar un formulario y enviar dicho formulario.

(REVISAR)

Pasar a JSON:
```java
ctx.json(CursosRepositorio.listar());
```
Manejar un pedido:
```java
var p = ctx.bodyAsClass(Curso.class);
ctx.formParam("apellidos", String.class).get());
```

**Objeto Java ↔ Base de Datos**

Hay dos escuelas de pensamiento:

1. **"ORM" (Object Relational Mapping)**:  Esto generalmente significa que  hay  un framework que realiza una conversión automática entre objetos Java y filas de la tabla de la base de datos.

    Hibernate, EclipseLink, OpenJPA implementan el estándar JPA. Es costoso configurar pero luego las cosas funcionan mágicamente. Pero, cuando la magia se rompe es difícil para el no experto arreglarla.

2. **"POJO" (Plain Old JavaObject)**: No usa un framework de mapeo, se hace un mapeo manual. Esto solía ser difícil, pero las nuevas sintaxis y bibliotecas lo hacen relativamente más fácil. Se debe invocar manualmente las consultas SQL para leer desde/hacia la base de datos.

# Ejemplos de APIs

- Documentación Spotify: https://developer.spotify.com/documentation/web-api/reference/
- Documentación MercadoLibre: https://developers.mercadolibre.com.ar/es_ar/api-docs-es
- Listado de APIs libres: https://github.com/public-apis/public-apis
