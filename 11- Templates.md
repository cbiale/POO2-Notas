Es posible disenar las pantallas usando un framework de front-end o motores de templates.

En los frameworks de front-end encontramos:
- AngularJS
- ReactJS
- VueJS
- Svelte
- etc.

En los motores de templates encontramos:
- jte (https://jte.gg/)
- Apache FreeMarker (https://freemarker.apache.org/)
- Apache Velocity (http://velocity.apache.org/)
- Thymeleaf (https://www.thymeleaf.org/)
- Pug4j (https://github.com/neuland/pug4j)
- Handlebars (https://github.com/jknack/handlebars.java)
- JMustache (https://github.com/samskivert/jmustache)
- MustacheJava (https://github.com/spullara/mustache.java)


## jte

Configuración del proyecto

Para usar jte, deben agregar la biblioteca como dependencia:

```xml
<dependency>
    <groupId>gg.jte</groupId>
    <artifactId>jte</artifactId>
    <version>1.0.0</version>
</dependency>
```

La extensión jte de Javalin viene desde Javalin 3.10.0, así que asegúrense de usar la última versión de Javalin:

```xml
<dependency>
    <groupId>io.javalin</groupId>
    <artifactId>javalin</artifactId>
    <version>3.11.0</version>
</dependency>
```

Vamos a renderizar nuestra primera plantilla. Creen el directorio `src/main/jte` en el proyecto. En este directorio creen un archivo `hola.jte` e ingresen lo siguiente:

```
Hola POO2 desde jte.
```

En el método `main` de nuestro proyecto ingresen:

```java
package app;

public class App {
    public static void main(String[] args) {
        Javalin app = Javalin.create().start(7000);

        app.get("/", ctx -> ctx.render("hola.jte"));
    }
}
```

Si van al navegador e ingresan en `http://localhost:7000` deben ver `Hola POO2 desde jte`.


> jte admite la recarga en caliente de plantillas.

## Manejo de errores

jte en caso de encontrar un error en la plantilla, por ejemplo esto puede darse si intentemos llamar a un método que no existe. En ese caso se va a producir una excepción de tipo `TemplateException` el cual nos indica el erro.

## Paso de parámetros

Para poder pasar datos a una plantilla se debe Crear una clase de datos, como por ejemplo:

```java
package app;

public class PaginaHola {
    public String nombreUsuario;
    public int documento;
}

Ahora, completemos ese objeto de página y lo pasamos a jte:

```java
package app;

public class App {
    public static void main(String[] args) {
        Javalin app = Javalin.create().start(7000);

        app.get("/", App::renderizarPaginaHola);
    }

    private static void renderizarPaginaHola(Context ctx) {
        var pagina = new PaginaHola();
        pagina.nombreUsuario = "admin";
        pagina.documento = 123456789;
        ctx.render("hola.jte", Collections.singletonMap("page", pagina));
    }
}
```

Ahora podemos usar el objeto de página en nuestra plantilla:

```html
@param app.PaginaHola pagina

<html lang="en">
<body>
    <p>Hola!</p>
    <p>El <b>usuario </b> conectado es ${pagina.nombreUsuario} (documento: ${pagina.documento})</p>
</body>
</html>
```

Ahora se necesita reiniciar el servidor. Una vez que actualice la página, deberían ver la nueva salida en el navegador.

## Plantillas de precompilación

Si ejecuta jte en un entorno que no sea de desarrollo, normalmente es una buena idea precompilar todas las plantillas.

De esta manera, si el proceso de compilación va a fallar en caso de que haya errores de compilación de jte.

En este caso la renderización de la plantilla es un poco más rápida.

La extensión Javalin jte permite personalizar el motor jte utilizado:

```java
public static void main(String[] args) {
    JavalinJte.configure(crearMotorDeTemplate());
    
    Javalin app = Javalin.create().start(7000);

    app.get("/", app::renderizarPaginaHola);
}

private static TemplateEngine crearMotorDeTemplate() {
    if (desarrollo) {
        DirectoryCodeResolver resolvedor = new DirectoryCodeResolver(Path.of("src", "main", "jte"));
        return TemplateEngine.create(resolvedor, ContentType.Html);
    } else {
        return TemplateEngine.createPrecompiled(Path.of("jte-classes"), ContentType.Html);
    }
}
```

`desarrollo` sería un booleano que determina si se está ejecutando un sistema de desarrollo o no. Mientras se desarrolla, jte necesita una forma de resolver los archivos de plantilla jte. Esto es lo que `DirectoryCodeResolver` hace. 

Cuando se ejecuta con plantillas precompiladas, esto no es necesario. En su lugar, necesitamos pasar el directorio que contiene todas las clases jte precompiladas.

A continuación, debemos asegurarnos de que todas las plantillas jte estén compiladas en maven. Esto es lo que hace el complemento `jte maven`. Agreguen lo siguiente a su `pom.xml`:

```xml
<plugin>
    <groupId>gg.jte</groupId>
    <artifactId>jte-maven-plugin</artifactId>
    <version>1.0.0</version>
    <configuration>
        <sourceDirectory>${basedir}/src/main/jte</sourceDirectory>
        <targetDirectory>${basedir}/jte-classes</targetDirectory>
        <contentType>Html</contentType>
    </configuration>
    <executions>
        <execution>
            <phase>process-classes</phase>
            <goals>
                <goal>precompile</goal>
            </goals>
        </execution>
    </executions>
</plugin>
```
Cuando abran el directorio `jte-class`, verán las clases Java generadas.

## Anexos

Documento basado en: https://javalin.io/tutorials/jte

Sintaxis de jte: https://github.com/casid/jte/blob/master/DOCUMENTATION.md

Sitio completo usando jte y javalin: https://github.com/casid/jte-javalin-tutorial

