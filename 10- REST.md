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

* **GET**: recupera un recurso específico *(por id)* o una colección de recursos.
* **POST**: crea un nuevo recurso.
* **PUT**: actualiza un recurso específico *(por id)*.
* **DELETE** - eliminar un recurso específico *(por id)*.

> Existen otros [verbos](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol#Request_methods)

Una solicitud HTTP, además de un verbo HTTP, normalmente consta de:

* un encabezado, que permite al cliente pasar información sobre la solicitud.
* un camino a un recurso.
* un cuerpo de mensaje opcional que contiene datos.

> Para poder enviar una solicitud a un servidor http dado se abre un socket de red para una dirección y puerto determinado. 

El servidor luego de tratar una solicitud devuelve una respuesta que incluye:

* Información del encabezado, incluido el código de estado.
    - 200 OK es el código HTTP que indica que todo ha salido bien.
    - 4XX para varios tipos de error.
    - Existen muchos otros, para ello vean el siguiente [enlace](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes).
  + Un cuerpo arbitrario: puede ser el código html de una página web, datos en formato JSON para una respuesta RESTful del servidor, un binario de imagen .jpg, etc.

# ¿Qué es la API RESTful? #

La interfaz de programa de aplicación *(API, Application Program Interface)* permite la interacción entre dos sistemas. Una API RESTful es una API que se ajusta al estilo REST y establece qué funcionalidades proporciona el servidor al cliente y cómo las proporciona.

## Servicios Web

La mayoría de las aplicaciones modernas de celular y web tienen un servicio RESTful en  segundo  plano que  controla toda  la  lógica empresarial subyacente: son  los"cerebros".

> **Un ejemplo de servidor RESTful básico**
>
> Un servicio web de carrito de compras que permite agregar un artículo al carrito, enumerar contenidos, eliminar un artículo, pagar, etc.

Un servicio web RESTful se ejecuta sobre el protocolo web http(s) estándar. Pero utiliza http como una  interfaz arbitraria: envía solicitudes arbitrarias *(no solo solicitudes de página web html/css/images)* y devuelve resultados arbitrarios *(no solo html/css/etc.)*. 

> La clave para un buen protocolo RESTful es una especificación clara de las solicitudes permitidas y las respuestas esperadas.

Un servidor web/servidor RESTful no es más que un proceso que escucha repetidamente las conexiones en un puerto TCP/IP *(generalmente 80 para http y 443 para https)*. Un navegador/cliente RESTful abre conexiones y envía solicitudes.

# ¿Qué es un punto final de API?

HTTP requiere que los datos se transfieran de un punto a otro a través de la red. Un punto final de API es el punto de entrada en un canal de comunicación cuando el cliente y el servidor interactúan.

## Recurso, ruta y punto final

Un punto final es un elemento de datos particular al que REST debe acceder *(por ejemplo, cursos)*.

Una ruta es un sufijo de URL para acceder al recurso necesario *(por ejemplo/cursos/5 para hacer referencia al curso con identificador 5)*.

Un punto final es una ruta más un método HTTP *(GET/PUT/DELETE/...)*.

Para ser 100% claros sobre el formato de solicitud/respuesta de los puntos finales admitidos por nuestra API, necesitamos escribir una especificación precisa *(documentar la API)*.

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

> Recomiendo lean [JSON MDN web docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON) y miren este [video](https://www.youtube.com/watch?v=iiADhChRriM).

# Entorno de Desarrollo de API

Una API *(Application Programming Interface)* establece qué funcionalidades proporciona el servidor al cliente y cómo las proporciona.

Una vez que se diseña la API, diferentes personas pueden trabajar en el servidor y en el cliente de forma independiente, incluso en paralelo, mientras ambas partes sigan la API, la aplicación funcionará al final.

Un **ADE (API Development Environment)** es de ayuda para diseñar la API, documentarla, probarla, interactuar con ella, etc. En la materia usaremos **Postman**. 

> Existen alternativas como Insomnia, SoapUI, Karate, etc.

Usamos una **ADE** porque el uso del navegador para enviar solicitudes HTTP *(y recibir la respuesta)* es engorroso, especialmente durante el desarrollo. 

**Postman** permite crear solicitudes GET, PUT, POST, etc., completas con cuerpos. También se puede utilizar para probar puntos finales automáticamente.

> Para profundizar sobre Postman puede ir al [Postman learning center](https://learning.postman.com/docs/) y ver el siguiente [tutorial](https://www.guru99.com/postman-tutorial.html).

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

Este término se refiere a la base de datos en el back-end: casi todos los servicios web sirven datos persistentes de algún tipo de base de datos. Dado que los datos están en una base de datos en un dispositivo de almacenamiento, el servidor puede caer y los datos no perderse *(evitando la perdida de datos)*.

## JSON ↔ Objeto Java ↔ Base de Datos

Existen tres representaciones diferentes de los mismos datos que deben conectarse. Esto es un problema clásico en aplicaciones web y telefónicas. Para dividir y  solucionar este  problema, es posible hacer dos  asignaciones independientes:

* JSON ↔ objeto Java 
* Objeto Java ↔ fila en la base de datos

Es posible simplificar estos pasos, pero recuerden: **separar las preocupaciones correctamente conduce a un código más robusto**.

**JSON ↔ Objeto Java**

En el controlador se deben realizar estás  conversiones. Asigne cada campo JSON a un campo *(atributo)* de un objeto Java. Jackson puede asignar  automáticamente un campo JSON a un campo Java en  ambas direcciones. En un POST podemos usar un formulario y enviar dicho formulario, o recibir datos en formato JSON.

Pasar a JSON:

``` java
    public void listar(Context ctx) throws SQLException {
        ctx.json(cursosRepositorio.listar());
    }
```

Recibir un argumento:

``` java
    public void borrar(Context ctx) throws SQLException, CursoNoEncontradoExcepcion {
        cursosRepositorio.borrar(cursosRepositorio.obtener(ctx.pathParam("identificador", Integer.class).get()));
        ctx.status(204);
    }
```

Recibir datos de un formulario:

``` java
    public void crear(Context ctx) throws SQLException {
        // Usando un formulario
        var c = new Curso(ctx.formParam("nombre", String.class).get());
        cursosRepositorio.crear(c);
        ctx.status(201);
    }
```

Recibir datos JSON:

``` java
    public void crear(Context ctx) throws SQLException {
        var c = ctx.bodyAsClass(Curso.class);            
        personasRepositorio.crear(c);
        ctx.status(201);
    }
```

**Objeto Java ↔ Base de Datos**

Hay dos escuelas de pensamiento:

1. **"ORM" (Object Relational Mapping)**:  Esto generalmente significa que  hay  un framework que realiza una conversión automática entre objetos Java y filas de la tabla de la base de datos.

    Hibernate, EclipseLink, OpenJPA implementan el estándar JPA. Es costoso configurar pero luego las cosas funcionan mágicamente. Pero, cuando la magia se rompe es difícil para el no experto arreglarla.

2. **"POJO" (Plain Old JavaObject)**: No usa un framework de mapeo, se hace un mapeo manual. Esto solía ser difícil, pero las nuevas sintaxis y bibliotecas lo hacen relativamente más fácil. Se debe invocar manualmente las consultas SQL para leer desde/hacia la base de datos.

En la materia vamos a usar **sql2o** o **JDBC**.

# Testing

## Introducción

Las  pruebas de  software son importantes, tomen  por  ejemplo  los millones  de dólares perdidos por la NASA por un error de conversión de unidades, si se hubieran realizado pruebas en el software este problema se hubiera detectado fácilmente.

La falta de pruebas puede causar un gran daño, en este caso financiero, pero a menudo incluso puede  afectar la  imagen  de una empresa, la idea que  los clientes tienen de un producto y, a menudo, estos daños pueden terminar siendo irreparables o muy difícil de arreglar.

No solo el error de software  en sí, sino las consecuencias de  ese  error pueden ser muy graves.

> Vean el siguiente [enlace](https://elpais.com/diario/1999/10/02/sociedad/938815207_850215.html).

## Pruebas de Software

Una  prueba  de  software  es  una  pieza  de  software, que  ejecuta  otra  pieza  de  software. Valida si ese código da como resultado el estado esperado *(prueba de estado)* o ejecuta la secuencia esperada de eventos *(prueba de comportamiento)*.

Las  pruebas  de  unidad  de  software  ayudan  al  desarrollador  a  verificar  que  la  lógica  de una  parte  del  programa  sea  correcta. La  ejecución  de  pruebas  automáticas ayuda  a identificar el software de regresiones introducidas por cambios en el código fuente.

Una prueba unitaria es una pieza de código escrita por un desarrollador que realiza una funcionalidad   específica   en   el   código   que   se   probará   y   afirma   un   determinado comportamiento  o  estado. El  porcentaje  de  código  que  se  prueba  mediante  pruebas unitarias  generalmente  se  denomina  **cobertura  de  prueba**. 

Una  prueba  unitaria  apunta  a una pequeña unidad de código, por ejemplo, un método o una clase.

## JUnit

Es  un framework de  prueba  que  utiliza  anotaciones  para  identificar  métodos  que especifican  una  prueba. Aunque  JUnit  se  usa ampliamente  para  pruebas  unitarias, también  se  usa  para  otros  tipos  de  pruebas, como  pruebas  funcionales o pruebas  de integración. A menudo, JUnit se utiliza como base para otro framework que realiza estas pruebas.

Una prueba en JUnit es un método contenido en una clase que solo se usa para pruebas *(clase  de  prueba)*, para  definir  que  cierto  método  es  un  método  de  prueba, se  debe anotarlo con la anotación *@Test*, este método ejecuta el código bajo prueba. 

Se utiliza  un  método  de  aserción, proporcionado  por  JUnit, para  verificar  un  resultado esperado  versus  el  resultado  actual.  Estas  llamadas  a  métodos  generalmente  se  llaman afirmaciones   o   declaraciones   de   afirmación. Se   deben proporcionar   mensajes significativos en las declaraciones de afirmación, eso facilita que el usuario identifique y solucione el problema.

> Recomiendo lean la [guía de usuario](https://junit.org/junit5/docs/current/user-guide/).

## Ejemplo

Si  se  desea  testear  una `Calculadora` se  debe  crear  una  clase `CalculadoraTest` y un método denominado `testSuma` donde se va a realizar la prueba y se pondrá la anotación `@Test` para que JUnit sepa que ese método es un método de prueba.

Dentro  del  método  de  prueba es  necesario ejecutar la funcionalidad  que se  quiere verificar. Para ello se debe crear el objeto de tipo `Calculadora` e invocar al método `suma` para poder sumar los valores 7 y 3 y devolver el resultado en una variable determinada.

En conclusión, si se está probando un método, tengo que ejecutarlo. Es importante tener en  cuenta  que es mandatorio crear  el  escenario  necesario  para  poder  realizar  esa funcionalidad.

Por último se debe comparar el resultado esperado con el  resultado obtenido, para ello se  debe  usar un método  de  aserción o afirmación *(assert)*, en JUnit existen varios métodos que se pueden usar. 

Lo  que  se  busca  es dejar de  imprimir  para  probar una  funcionalidad, es  mejor crear pruebas automatizadas.

``` java
public class CalculadoraTest {
    @Test
    public void testSuma () { 
        // creo un objeto sobre el que quiero realizar una prueba
        var calculadora = new Calculadora(); 
        // Directivas de aserción o afirmación 
        assertEquals(10, calculadora.sumar(7, 3), "7 + 3 = 10");
    }
}
```

## Prueba de puntos finales con OkHttp

Las pruebas de API son un tipo de prueba de software que implica probar las interfaces de programación de aplicaciones (API) directamente y como parte de las pruebas de integración para determinar si cumplen con las expectativas de funcionalidad, confiabilidad, rendimiento y seguridad.

Cuando se trata de probar puntos finales de API, pueden hacerlo de forma manual o automática. **Postman** ofrece funcionalidades para ambos. También hay bibliotecas de Java que ayudan con las pruebas de API, una biblioteca cliente http liviana es [**OkHttp**](https://square.github.io/okhttp/) para pruebas funcionales en forma de pruebas unitarias. 

Para otros tipos de pruebas, por ejemplo, confiabilidad, rendimiento, etc. es posible usar Postman.

## Pruebas funcionales con OkHttp

Se debe agrega la siguiente dependencia en Maven: `com.squareup.okhttp3: okhttp: 4.9.0` .

Luego, se debe agregar una nueva clase `JUnit` en `test/java` para probar nuestros puntos finales. Llamémosla `RESTAPITest.java` con el siguiente contenido:

```java
import okhttp3.*;
import org.junit.BeforeClass;
import org.junit.Test;
import java.io.IOException;
import java.sql.*;
import static org.junit.Assert.*;

public class RESTAPITest {
    static OkHttpClient client;
    
    @BeforeClass
    public static void beforeClassTests() throws SQLException {
        cliente = new OkHttpClient();
    }

    @Test
    public void testListarCursos() throws IOException {
        Request requerimiento = new Request.Builder()
                .url("http://localhost:7000/cursos")
                .build();
        Response respuesta = cliente.newCall(requerimiento).execute();
        assertEquals(200, respuesta.code());
    }
}
```

Primero, debemos asegurarnos de crear una instancia de un `cliente` de la clase `OkHttpClient`. Necesitamos hacer esto solo una vez, antes de que se ejecuten las pruebas. Luego, podemos escribir solicitudes y enviarlas a través del cliente instanciado. En el ejemplo, tenemos una prueba, prueba el punto final de la API de `cursos`.

Hasta ahora solo confiamos en el código de estado devuelto para saber que los puntos finales están funcionando como se esperaba. Idealmente, también se deben agregar aserciones para verificar que el contenido devuelto sea correcto.

> Consulten el sitio web de OkHttp para ver varios ejemplos y documentación detallada.

# Ejemplos de APIs

* Documentación Spotify: https://developer.spotify.com/documentation/web-api/reference/
* Documentación MercadoLibre: https://developers.mercadolibre.com.ar/es_ar/api-docs-es
* Listado de APIs libres: https://github.com/public-apis/public-apis
