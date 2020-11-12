#Principios de Diseño

## Introducción

Veremos una colección de principios de diseño para hacer un mejor software. Cada gran programador tiene una caja de herramientas de principios de diseño que usan para ayudarles a producir un gran código.

Debemos considerar que estos principios son confusos y no son mutuamente excluyentes. Por ello, deben aprenderse mediante ejemplos / experiencias de codificación específicos.  

## Análisis Básico y Principios de Diseño

Estos son algunos principios básicos de diseño que probablemente ya haya escuchado:
- El software bien diseñado es más fácil de depurar, cambiar y ampliar.
- Códificar para interfaces, no implementaciones.
- Compartir el comportamiento común a través de la herencia.
- Si el diseño está demostrando ser inflexible, debe ser refactorízado con el objeto de restaurarlo para que sea un buen diseño _(lo veremos más adelante)_.
- Las clases deben ser __cohesivas__: la clase debe tener un único propósito claramente establecido que se ajuste a su nombre y a todos sus atributos y métodos.
- De igual forma, el nombre de los métodos debe representar todo lo que hace.
- Separación de preocupaciones o intereses: no deben existir muchas preocupaciones diferentes en una clase; en cambio, diferentes tareas / aspectos deberían estar en diferentes clases / funciones.
    >  Relacionado con el Principio de Responsabilidad Unica, pero en este la responsabilidad es única.

---

## SOLID

- SOLID _(__S__ ingle responsibility, __O__ pen-closed, __L__ iskov substitution, __I__ nterface segregation and __D__ ependency inversion)_ es un acronimo creado por Robert C. Martin.

Presenta 5 principios básicos de programación orientada a objetos, si se siguen estos principios lograremos tener un buen diseño de programación legible y mantenible.

Todos estos se reducen a cohesión _(alta)_, acoplamiento _(bajo)_ y reutilización.

> Enlace: https://en.wikipedia.org/wiki/SOLID


## Principio de Responsabilidad Única

> Una clase debe tener una y solo una responsabilidad.

Este principio es similar al principio de cohesión y a la separación de preocupaciones.

- _Ejemplo_ : En la aplicación de Cursos se separaron las responsabilidades: enrutamiento _(clase Servidor)_, procesamiento de solicitudes _(Controladores)_, datos reales _(clases del modelo)_ y persistencia _(repositorios)_.

Este principio habría sido violado si hubiéramos fusionado estas clases. En la forma en que lo codificamos, cada clase tiene una responsabilidad, resumida por el nombre de la clase.

__Los diseños centrados en datos siempre violan este principio__.


_Regla general_: si no puede describir la responsabilidad de la clase en 25 palabras o menos, puede tener más de una responsabilidad.

Proporciona un indicador de cuándo dividirse en varias clases.

> Utilidad: https://www.spinellis.gr/sw/ckjm/
> - Permite medir: __LCOM (Lack of cohesion in methods)__
> - Grado en que los elementos de una clase están relacionados.
> - Los métodos están relacionados si acceden al mismo subconjunto de variables de instancia o clase, o si uno llama al otro.
> - Detecta grupos no relacionados dentro de una clase.
> - Alto LCOM sugiere posible violación de responsabilidad única.


La cohesión mide el grado de dependencia entre clases / módulos en un sistema. Donde:

- _Alta cohesión_: las clases/módulos en el programa realizan tareas similares y están relacionadas entre sí _(a través de asociaciones)_ __¡BUENO!__.

- _Baja cohesión_: muchas clases/módulos diversos y auxiliares, sin asociaciones __¡MALO!__.


## El Principio Open-Closed

> "Las entidades de software _(clases, módulos, funciones, etc.)_ deben estar abiertas para la extensión, pero cerradas para la modificación". Bertrand Meyer


Abierto para extensión significa que el módulo debe poder ampliarse con un nuevo comportamiento.

Cerrado para modificación significa que no es necesario tocar el módulo para agregar la extensión.

El polimorfismo hace que esto sea posible, permite escribir código nuevo que funcione con código antiguo sin tener que tocar el código antiguo.


Hay que esforzarse en escribir código que no tenga que cambiarse cada vez que cambien los requisitos.

La herencia con sobreescritura significativa puede violar este principio, dado que __sobreescribir es modificar__:

- Se debe favorecer la composición sobre la herencia _(otro principio)_: use la composición para "conectar" la parte que incorpora la extensión.
- Permitir subclases pero declarar casi todos los métodos como final para limitar o eliminar en gran medida la sobreescritura.

> __Los diseños de bibliotecas y frameworks deben seguir estrictamente este principio__.


¿Cuando debemos de aplicar el principio? 

Si el método/clase se ha modificado durante la construcción del software o si se sabe que con el paso del tiempo se agregaran nuevas funcionalidades al mismo.


Ejemplo, consideremos la siguiente clase:

```java
public class Rectangulo {
    private double ancho;
    private double alto;
    public void setAncho(double ancho) { ... }
    public void setAlto(double alto) { ... }
    public double getAncho() { ... }
    public double getAlto() { ... }
}
```
--

```java
public class CalculadorArea {
    public double Area(Rectangulo[] figuras) {
        double area = 0;
        for (Rectangulo figura : figuras) {
            area += figura.getAlto() * figura.getAncho();
        }
        return area;
    }
}
```

Que pasa si ahora quisieramos aceptar Circulos y Rectangulos en la clase `CalculardorArea`.


```java
public class CalculadorArea {
    public double Area(Object[] figuras) {
        double area = 0;
        for (Object figura : figuras) {
            if (figura instanceof Rectangulo) {
                Rectangulo r = (Rectangulo) figura;
                area += r.getAlto() * r.getAncho();
            } else {
                Circulo c = (Circulo) figura;
                area += c.getRadio() * c.getRadio() * Math.PI;
            }
        }
        return area;
    }
}
```

Y si se quiere ahora calcular triángulos...


Una forma que esto cumpla con el principio es:

```java
public abstract class Figura {
    public abstract double getArea();
}
```

```java
public class Rectangulo extends Figura {
    private double ancho;
    private double alto;
    public void setAncho(double ancho) { ... }
    public void setAlto(double alto) { ... }
    public double getAncho() { ... }
    public double getAlto() { ... }
    @Override
    public double getArea() {
        return alto * ancho;
    }
}
```

```java
public class Circulo extends Figura {
    private double radio;
    public void setRadio (double radio) { ... }
    public double getRadio() { ... }
    @Override
    public double getArea() {
        return radio * radio * Math.PI;
    }
}
```

```java
public class CalculadorArea {
    public double Area(Figura[] figuras) {
        double area = 0;
        for (Figura figura : figuras) {
            area += figura.getArea();
        }
        return area;
    }
}
```

## Principio de Sustitución de Liskov

> Los objetos de subclase siempre deben ser sustituibles por objetos de superclase.

Principio más importante en el diseño orientado a objetos.

La formulación es atribuida a Barbara Liskov _(ganador del premio Turing)_ https://en.wikipedia.org/wiki/Barbara_Liskov.

Causas _(hediondez del código)_:
- Una subclase sobreescribe destructivamente un comportamiento heredado de su superclase.
- Fuerza cambios a la superclase para evitar el problema.
- Las subclases que no aprovechan las implementaciones de las superclases no deberían ser subclases.
- __Indica uso inapropiado de la herencia__.

Un contraejemplo:

```java
public class Rectangulo {
    public void setAncho(double ancho) { ... }
    public void setAlto(double alto) { ... }
    public double getArea() { ... }
}
```


```java
public class Cuadrado extends Rectangulo {
    @Override
    public void setAncho(double ancho) {
        super.setAncho(ancho);
        super.setAlto(ancho);
    }
	
    @Override
    public void setAlto(double alto) {
        super.setAncho(alto);
        super.setAlto(alto);
    }
}
```

Sabemos por de matemáticas que un cuadrado _"es un"_ rectángulo. Los métodos `setAncho` y `setAlto` sobreescritos en `Cuadrado` imponen que ancho == alto.


Que pasa con lo siguiente:

```java 
static void ejemplo() {
    var rectangulo = new Rectangulo();
    rectangulo.setAlto(5);
    rectangulo.setAncho(2);
    System.out.println("Area de rectangulo: " + rectangulo.getArea());
    var cuadrado = new Cuadrado();
    cuadrado.setAlto(5);
    cuadrado.setAncho(6);
    System.out.println("Area de cuadrado: " + cuadrado.getArea());
}
```

Esto se soluciona creando dos clases que se encuentren obligadas a implementar `getArea()`.

Para que se mantenga el principio, __todas__ las clases derivadas deben ajustarse al comportamiento que los clientes esperan de la clase base.

## Principio de Segregación de Interfaces

> Los clientes no deben verse obligados a depender de métodos _(heredar o implementar)_ que no usan.
> Los clientes de un programa dado sólo deberían conocer de éste aquellos métodos que realmente usan, y no aquellos que no necesitan usar.


Tiene por finalidad mantener un sistema desacoplado de los demás sistemas de los cuales depende. Un correcto uso de interfaces puede evitar este problema.



Se debe dividir las interfaces grandes en otras más pequeñas y específicas.


El alto acoplamiento de código se correlaciona con mayores costos de mantenimiento de software. El código es más difícil de modificar, refactorizar, extender

El acoplamiento mide las dependencias entre subsistemas, donde:
- _Alto acoplamiento_ : los cambios en un subsistema tendrán alto impacto en el otro subsistema __¡MALO!__. Dado que requiere cambio de modelo, compilación masiva.
- _Acoplamiento bajo_: el cambio en un subsistema no afectar a cualquier otro subsistema __¡BUENO!__.


Ejemplo:

```java
public interface IReloj {
    public String getTiempo();
    public String getNotificacionesEmail() throws Exception;
}
```

Se implementa un reloj inteligente:

```java
public class RelojInteligenteImpl implements IReloj {
    @Override
    public String getTiempo() {
        SimpleDateFormat formato = new SimpleDateFormat("hh:mm:ss");
        System.out.println(formato.format(new Date()));
        return formato.format(new Date());
    }

    @Override
    public String getNotificacionesEmail() throws Exception {
        return "Tiene 2 emails";
    }
}
```

Se implementa un reloj normal: donde se debe propagar una excepción.


```java
public class RelojNormalImpl implements IReloj {
    @Override
    public String getTiempo() {
        SimpleDateFormat formato = new SimpleDateFormat("hh:mm:ss");
        System.out.println(formato.format(new Date()));
        return formato.format(new Date());
    }
    
    @Override
    public String getNotificacionesEmail() throws Exception {
        throw new Exception("Funcionalidad inexistente");
    }
}
```

Esto se resuelve creando interfaces mas pequeñas y asi cumplimos con el principio de segregación de interfaces.

- Interfaces:

```java
public interface IRelojNormal {
    public String getTiempo();
}
```

```java
public interface IRelojInteligente extends IRelojNormal {
    public String getNotificacionesEmail() throws Exception;
}
```

- Clases:

```java
public class RelojInteligenteImpl implements IRelojInteligente {
    @Override
    public String getTiempo() {
        SimpleDateFormat formato = new SimpleDateFormat("hh:mm:ss");
        System.out.println(formato.format(new Date()));
        return formato.format(new Date());
    }
	
    @Override
    public String getNotificacionesEmail() throws Exception {
        return "Tiene 2 emails";
    }
}
```

```java
public class RelojNormalImpl implements IRelojNormal {	
    @Override
    public String getTiempo() {
        SimpleDateFormat formato = new SimpleDateFormat("hh:mm:ss");
        System.out.println(formato.format(new Date()));
        return formato.format(new Date());
    }
}
```


## Principio de Inversión de Dependencias

> No dependas de clases concretas, depende de abstracciones.

Las clases de alto nivel no deberían depender de las clases de bajo nivel. Ambas deberían depender de las abstracciones.

Las abstracciones no deberían depender de los detalles. Los detalles deberían depender de las abstracciones.

__Esto básicamente significa__: programa para una interfaz, no a una implementación particular de la interfaz.

Contraejemplo:

```java
public class ServicioFacturacion {
    public Recibo cargarOrden(OrdenPizza orden, TarjetaCredito tarjeta) {
        ProcesadorTarjetaCreditoPaypal procesador = new ProcesadorTarjetaCreditoPaypal();
            ...
    }
}
```

Existe una dependencia de la implementación particular del procesador de tarjeta de crédito.

En este caso el `new` es un código hediondo...

Refactorización:


```java
public interface ProcesadorTarjetaCredito { 
    ... 
}
```

```java
public class ServicioFacturacion {
    private final ProcesadorTarjetaCredito procesador;

    public ServicioFacturacion (ProcesadorTarjetaCredito procesador) {
        this.procesador = procesador;
    }

    public Recibo cargarOrden (OrdenPizza orden, TarjetaCredito tarjeta) {
        ...
    }
}
```

Ahora `ServicioFacturacion` depende de la interfaz `ProcesadorTarjetaCredito`, no de una implementación particular.

Hemos eliminado el `new` al pasar una instancia de `ProcesadorTarjetaCredito` en el constructor. Esto ahora satisface el principio porque se puede extender `ServicioFacturacion` para trabajar con procesadores de tarjetas de crédito adicionales sin modificarlo.


## No te Repitas (Don't Repeat Yourself)

> Evite el código duplicado: resuma cosas en común en una sola ubicación.

Encontrar esto es fácil, se da cuando se repiten bloques de código casi idénticos.

Si no se cumple, se va a tener dos bases de código paralelas para tratar de mantener la coherencia y, a menudo, esto falla.


Y puede que esto se convierta en tres, cuatro o x lugares donde se repite el código.

Se puede resolver moviendo el código a un método común, creando una superclase común, etc.

## Diseño por Contrato y Programación Defensiva

Estos principios son sobre la fiabilidad. Existen fundamentalmente dos enfoques _(no mutuamente excluyentes)_ para hacer que el software sea más confiable.

- __Diseño por contrato__: escriba un contrato claro sobre cómo se supone que debe utilizar el llamante del método y ​​suponga que el llamante es disciplinado y obedece el contrato para, por ejemplo, no pasar un objeto nulo.

- __Programación defensiva__: el escritor de la biblioteca es cauteloso y se protege contra los llamantes que llaman incorrectamente al método, por ejemplo, pasar objetos nulos al verificar explícitamente esa condición y tomar las medidas adecuadas.

En el diseño por contrato se pone la responsabilidad en el _llamante_ y en la programación defensiva se pone la responsabilidad en el _llamado_ para que se cumpla con la especificación.


## El Principio de Bajo Acoplamiento

> Esfuércese por realizar diseños débilmente acoplados entre objetos que interactúan

Los diseños débilmente acoplados permiten construir sistemas orientados a objetos flexibles que pueden manejar los cambios porque minimizan la interdependencia entre objetos.

__Un principio más profundo__: Cuanto más complejo es el sistema, más débilmente acoplado, autónomo y multicapa debe ser.

Por ejemplo: MVC en general ilustra las ventajas de este principio.

Beneficios

- Los cambios en otros componentes no afectan.
- Clases fáciles de entender por separado.
- Clases fáciles de reutilizar.

## El Principio de Menor Conocimiento

> Habla solo con tus amigos inmediatos (Ley de Demeter).


- Evite realizar lo siguiente:

```
unaVentana.getPanel().getRasterizador().setFrecuenciaActualizacion(60);
```

El código es más complicado si demasiados objetos interactúan directamente entre sí, y es más probable que se introduzcan errores a medida que el código evoluciona con el tiempo.

__Solución__: dejar que el _amigo_ compartido sea un intermediario en lugar de introducir muchas dependencias de largo alcance.

```
unaVentana.usarAltaFrecuenciaActualizacion();
```

Esto está relacionado con el principio de bajo acoplamiento, las cosas cercanas se acoplan estrechamente y las cosas lejanas se acoplan libremente.

Beneficios:

- Se reducen las dependencias entre clases y el acoplamiento.
- Se vuelve más sencillo reutilizar las clases.
- El código es más fácil de probar.
- El código es más mantenible, más flexible a los cambios.

