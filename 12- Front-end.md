# Navegadores

Cada navegador tiene dos componentes principales:

- Un motor de renderizado que analiza HTML y CSS para mostrar la información
- Un motor de JavaScript que interpreta el código JS en un entorno de ejecución de espacio aislado

La API está estandarizada en todos los navegadores: la mayoría de I + D se trabaja en el rendimiento.


## Conceptos Básicos de HTML

**HTML = Hyper Text Markup Language**

Los archivos deben comenzar con `<!DOCTYPE html>`.  El documento es un árbol de etiquetas de apertura y cierre, con una etiqueta `<html>` como raíz. Ejemplo de par de etiquetas de apertura / cierre: `<div>` `</div>`. Los pares abiertos / cerrados pueden tener texto o más etiquetas entre ellos. Algunas etiquetas son "independientes" y no necesitan cerrarse: `<link>`, `<meta>`, `<img>`. Las etiquetas pueden tener atributos, como _"id"_ o _"clase"_:

```html
<div class = "clase" id = "1">
    Soy un texto dentro de un div.
</div>
```
### Ejemplo

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <link rel="stylesheet" href="estilo.css">
        <title>POO2</title>
    </head>
    <body>
        <h1>Hola Mundo</h1>
        <p>
            Esto es un texto...
        </p>
    </body>
</html>`
```

---

## Etiquetas

Entre las etiquetas encontramos:
- Divs `<div>` divide el documento en diferentes secciones.
- Los encabezados (`<h1>`, `<h2>`, ...) son para encabezados de sección, incluido el título general de la página.
- Los párrafos (`<p>`) dividen el texto en párrafos.
- Los saltos de línea (`<br>`) indican saltos de línea.
- Las etiquetas de anclaje (`<a>`) se utilizan para vincular a otras páginas.
- Los espacios (`<span>`) denotan texto que de alguna manera es diferente o importante, como texto en negrita o caracteres especiales.
- Las etiquetas de imagen (`<img>`) muestran imágenes.
- Los formularios (`<form>`) se usan para formularios web, junto con etiquetas relacionadas como `<input>` y `<textarea>`.

**Luego vamos a ver otras etiquetas**

> **Referencias**
> 
> - [MDN web docs](https://developer.mozilla.org/en-US/docs/Web/HTML)
> - [w3schools](https://www.w3schools.com/html/)



## CSS: hacer bonito a HTML

El HTML que hemos visto hasta ahora es bastante feo: necesitamos una forma de cambiar cómo se muestra si queremos crear un sitio web atractivo. Es posible hacer esto con CSS, que es otro lenguaje de marcado que le dice a un navegador cómo mostrar una página HTML. Hay demasiadas propiedades CSS , MDN tiene recursos que nos permite buscar por propiedades específicas.

> **Referencias**
>
> - [Estilos html](https://www.w3schools.com/html/html_styles.asp)
> - [Formateando html](https://www.w3schools.com/html/html_formatting.asp)
> - [MDN sobre CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)

### Conceptos Básicos de CSS

CSS funciona aplicando reglas para cambiar el estilo de los elementos. Por ejemplo:

```css
strong {
    color : red;
}
```

La regla comienza con un selector, `strong`, que indica que se aplica a elementos `<strong>`. La parte interior de las llaves es la declaración: el cuerpo de la regla. La palabra clave `color` es una propiedad y _red_ es un valor. Los puntos y comas se usan para separar pares propiedad-valor.

### Selectores

El selector CSS más básico es el nombre de la etiqueta. Para hacer que todo el texto del cuerpo sea negro, por ejemplo, se debe hacer:

```css
body {
    color: #000000;
}
```

Los otros selectores básicos trabajan en dos atributos especiales: clase `class` e id `id`.


```css
/* Selector de clase */
.red-text {
    color: #FF0000;
}

/* Selector por id */
#blue-div {
    color: #0000FF;
}
```


### Librerías

Algunas librerías que podemos usar son:
- Bootstrap: http://getbootstrap.com/
- Foundation: https://foundation.zurb.com/
- Bulma: https://bulma.io/
- Skeleton: http://getskeleton.com/
- Pure: https://purecss.io/
- Materialize: https://materializecss.com/
- Cardinal: https://cardinalcss.com/
- Semantic UI: https://semantic-ui.com/


## Javascript en el navegador

En el navegador, necesitamos usar una etiqueta especial `<script>`.

```html
<body>
	<!-- contenido y cosas ->
	<script src = "ruta/a/script.js"> </script>
</body>
```

Los navegadores cargan las etiquetas secuencialmente, por lo que es una buena práctica colocar las etiquetas del script en último lugar. De esa forma, los usuarios verán la página HTML básica más rápidamente.

## DOM

**DOM = Document Object Model**

Árbol de objetos JavaScript que representa el documento HTML, llamados nodos DOM. Permite cambiar dinámicamente la página usando JavaScript.

### Ejemplo

```html
<!DOCTYPE html>
<html>
    <head></head>
    <body>
        <p>parrrafo</p>
        <div>div...</div>
    </body>
</html>
```


### Eventos del navegador

Las interacciones del usuario se modelan con un sistema basado en eventos; los navegadores tienen una API de JavaScript para conectarse a estos eventos. Las funciones se registran como oyentes de eventos y reciben argumentos con información del evento _(por ejemplo, qué tecla se presionó)_.

Eventos diferentes:

- Mouse: mousedown, mouseup, click, dblclick, mousemove, mouseover, mousewheel, mouseout, contextmenu
- Touch: touchstart, touchmove, touchchend, touchcancel
- Teclado: keydown, keypress, keyup
- Forms: focus, blur, change, submit
- Ventana: scroll, resize, hashchange, load, unload


### Manejadores en HTML

Es técnicamente posible definir controladores de eventos directamente en su HTML de la siguiente manera:

```html
<button class = "submit" onclick = "enviarFormulario();">
	Enviar
</button>
```

Es recomendable usar código javascript en archivos separados _(.js)_.
O usar librerías como Jquery: https://jquery.com/

Alternativas a Jquery

- UmbrellaJS: https://umbrellajs.com/
- ZeptoJS: https://zeptojs.com/
- ChibiJS: https://github.com/kylebarrow/chibi
- Cash: https://github.com/kenwheeler/cash
- Javascript _(Mejoras importantes desde ES6)_

# Javascript

Veremos una introducción rápida a Javascript.

## Literales

- Números: `1, 2, 3, 1.28e4, NaN, Infinity`
- Cadenas: `'xyz', 'foo \n', '\u2603'`
- Booleanos: `true, false`
- Arreglo: `[1, 2, 'hola', 'spam']`
- Objeto: `{curso: 'POOII', tema: 'JavaScript'}`
- Funciones:

```js
var cuadrado = function (x) {
	return x * x;
}
```

## Operadores

- Aritméticos: `+, -, *, /, %`
- Comparación: `<, <=, >, >=, ==, ===, !=, !==`
- Lógico: `&&, ||, !`
- Concatenación: `+`
- Bits: `&, |, ~`


## typeof

Como su nombre lo indica, `typeof` retorna el tipo de la variable que se le pasa.

```js
typeof(1);
typeof('string');
typeof([1, 2, 'hola', 'spam']);
```

## Arreglos

Los arreglos son técnicamente objetos. Se puede testear explícitamente si es un arreglo usando:

```js
Array.isArray(arreglo);
```

## Números

Se almacenan internamente como un valor de 64-bit _(como el tipo double en Java)_:

Otros números son:
- `NaN` represente el resultado de un valor que no es un número. Por ejemplo `Number('xyz')` retorna `NaN`. No se puede comparar usando operadores de igualdad, solo mediante `Number.isNaN()`.
- `Infinity` representa todos los valores mayores a `Number.MAX_VALUE`.


## Cadena de caracteres

Las cadenas de caracteres se pueden escribir con comillas simples o comillas dobles. 

> Use comillas simples: es un mal estilo mezclarlas.

**Excepción**: cadenas como `"Me gustan las comillas simples ', no me gustan las comillas dobles"` que tienen comillas simples dentro de ellas.

Los caracteres de escape usan barra invertida, como en Java: `\n \t \\`.

Las cadenas son inmutables: una vez creadas, no pueden ser cambiadas. Si se concatenan con el operador `+` se devuelve una nueva cadena. No existe el tipo `char`.

Se dispone de muchos métodos o propiedades útiles: `.length`, `substring()`, `toLowerCase()`, `toUpperCase()`, etc.

## Booleanos

- `true` y `false`. Operadores lógicos estándar (`&&`, `||`,`!`). También operadores a nivel de bit (`&`, `|`, `~`)

> **Advertencia**
>
> JavaScript puede usar CUALQUIER VALOR con un operador lógico.
> 
> Valores falsos: _false_, _null_, _undefined_, _0_, _NaN_, _''_
>
> Cualquier otro valor es verdadero _(incluyendo 'false', [], {})_

## Igualdad y Coerción

Existen dos comparadores `==` vs `===`.

> Regla de oro, usar `===`

¿Por qué? 

`==` es una comparación de igualdad abstracta, intentará forzar a ambas partes al mismo tipo y hará la comparación.

`===` es la estricta comparación de igualdad, no intentará forzar a ambas partes al mismo tipo para hacer la comparación. Solo compara directamente.


Ejemplo:

```
console.log (3 == "3"); // verdadero.
console.log (3 === "3"); // falso.
```

Pero cuando se habla de objetos, ambos `==` y `===` devolverán false a menos que ambos lados se refieran exactamente al mismo objeto.

## Arreglos

La notación literal usa corchetes: 

```
['hola', 'mundo', 'poo2'];
```

Puede ser heterogéneo: 

```
['poo2', 1, true];
```

A los elementos se accede con notación de corchetes: 

```
arreglo[0];
```

Debido a que los arreglos son instancias de objetos, **¡se pasan por referencia a funciones!**.

Métodos interesantes como `push()`, `pop()`, `slice()`, `shift()`, `unshift()`.


## Objetos

Almacenamientos clave-valor mutables. La notación literal usa llaves: 

```js
{
    nombre: 'Pepe', 
    'id': 1
}    
```

Los nombres de propiedad pueden ser cadenas: 

```js
{
    'nombre': 'Pepe'
}
```
  
Acceso con `objeto.nombrePropiedad` u `objeto['nombrePropiedad']`

Ejemplo:

```js
var obj = {
    unaPropiedad: 'abcdef',
	objetoAnidado: {a: 1, b: 2, c: 3},

	func: function () {
		return 0;
	}
}

obj.unaPropiedad;       // -> 'abcdef'
obj['objetoAnidado'].a; // -> 1
```

## Funciones

Son objeto JavaScript de primera clase **(esto permite que JavaScript aproveche las técnicas de programación funcional)**.

Las funciones pueden devolver un valor con la palabra clave `return`. Si no se devuelve ningún valor, la función devuelve `undefined`.

Ejemplo:

```js
var cuadrado = function (x) {
	return x * x;
}
```

### Definiendo Funciones

```js
function Nombre (parámetros) { 
    // cuerpo 
}
```

Si se excluye el nombre la función se transforma en anónima.

```js
var anonima = function(x) {
	return x + x;
}
```

Si se nombra a la función, se proporciona más trazas de pila informativas en caso de errores.

```js
var funcDoble = function Doble (x) {
    return x + x;
}
```

### Funciones vs Llamadas

No se debe confundir la diferencia entre una llamada a función y la función misma, la llamada siempre terminará con algunos paréntesis.

```js
var cuadrado = function (x) {
    return x * x;
}

console.log(cuadrado); // función 
console.log(cuadrado(2)); // llamada
```

## Bucles

For loop:

```js
for (var i = 0; i < Infinity; i++) {
	console.log('Hola...')
}
```

While loop:

```js
var logico = true
while (logico) {
	console.log('Hola...')
}
```

## Closures

Las variables permanecen dentro del alcance cuando se crea una función anidada. Por ejemplo, la variable `x` a continuación todavía está disponible en la función `y`.

```js
var unaFuncion = function () {
	var x = 123;
	var y = function () {
		console.log (x);
	};
	y ();
};

unaFuncion() // -> 123
```

Son muy útiles para crear estados privados, variables a las que ningún código externo puede acceder. 

```js
var crearContador = function () {
	var contador = 0;
	return function () {
		contador++;
		return contador;
	};
};

var contar = crearContador();
console.log(contar()); // --> 1
console.log(contar()) // --> 2
```

## Objetos

Todo es un objeto Aparte de los tipos de datos primitivos *(`String`, `boolean` y `Number`)*, todo en JS es un tipo de objeto.

Incluso los tipos primitivos pueden comportarse como objetos *(`String`, por ejemplo, tiene propiedades/métodos)*.

Un arreglo es un objeto con claves enteras y dispone de métodos específicos.

Las funciones también son similares a objetos y pueden tener propiedades y métodos, pueden considerarse como objetos ejecutables.

## El Objeto Global

Si una función no está asignada a un objeto, entonces este contexto será el objeto global.

Si una variable no se declara dentro de una función, se asigna al objeto global.

## Uso de this

Si una función es una propiedad de un objeto, entonces se puede acceder al objeto padre desde esa función usando `this`.

```js
var obj = {
	propiedad : 1,
	printPropiedad : function () {
		console.log(this.propiedad++);
  	}
};

obj.printPropiedad();
obj.printPropiedad();
obj.printPropiedad();
```


## bind()

- Mediante el uso de _bind()_ se asigna manualmente a la función interna el contexto correcto.

```js
var imprimirNumero = {
	numero : 3,
	imprimir2xNumero : function () {
		var doblar = function () {
			return 2 * this.numero;
		}.bind(this); 
		console.log(doblar());
	}
};

imprimirNumero.imprimir2xNumero();
imprimirNumero.imprimir2xNumero();
```

## ¿Qué es la programación asincrónica?

La mayoría de los programas que se escriben son programas sincrónicos. Se escribe código y cada línea se ejecuta una tras otra. Sin embargo, este no es un buen modelo para situaciones en las que necesita esperar a que suceda algo, o cuando desea que sucedan dos cosas a la vez. En ese caso se necesita de la programación asincrónica. 

Se usa cuando:

- Un usuario hace clic en un botón.
- Hacer una solicitud HTTP a un sitio web.
- Obtener datos de una base de datos.

**Ejemplos**:

- Sincrónico:

```js
var sincronico = function() { 
	console.log('uno');
	console.log('dos');
}

sincronico();
```


- Asincrónico:

```js
var asincronico = function() {
	console.log('uno');
	setTimeout(
		function() { 
			console.log('luego') 
		}, 5000
	);
	console.log('dos');
}

asincronico();
``` 


## Callback

- Es una función asociada a una llamada asincrónica. Se pasa como argumento a otra función con el objetivo que se ejecute una vez que una tarea asincrónica finalice.


```js
var cb = function () {
	console.log('callback!');
};
// espera 500ms, luego ejecuta cb
setTimeout(cb, 500);

```

## Clases en ES6

ES6 introduce una sintaxis azucarada para trabajar con clases mediante la palabra reservada `class`. Para construir un prototipo `Gato` que extiende de `Animal` se puede hacer mediante:

```js
class Gato extends Animal {
	constructor (propiedadAnimal, propiedadGato) {
		super(propiedadAnimal);
		this.propiedadGato = propiedadGato;
	}
}
```

Donde: `constructor()` es usado para invocar el código que se debe ejecutar cuando se construye un gato. `super()` se usa para invocar al constructor del padre.


## Métodos de clase en ES6

También se puede definir métodos de clase con sintaxis ES6.

```js
class Auto {
	constructor () {/* */}

	conducir() {
		console.log('se conduce');
	}

	static esAuto(c) {
		return c instanceof Auto;
	}
}

let ford = new Auto();
ford.conducir();
console.log(Auto.esAuto(ford));
```

Hay dos formas de definir métodos. `conducir()` se invoca usando un objeto.

`esAuto()` se define como estático, por lo que se llama usando la clase `Auto`.

## let y const

ES6 presenta una nueva sintaxis para definir variables. La palabra clave `let` es como `var`, excepto que `let` tiene un alcance de bloque mientras que `var` tiene un alcance de función. 

> Este es probablemente el comportamiento al que ya estamos acostumbrados desde otros lenguajes de programación. 

La palabra clave `const` también tiene un alcance de bloque, pero las variables declaradas con `const` no pueden reasignarse después de inicializarse.


```js
for (let i = 1; i < 4; i++) {
	console.log(i);
}
console.log(i); //Error
```

El código anterior funcionaría si se usa `var`.


## Funciones de Flecha

Las funciones de flecha se escriben con la sintaxis `() => {}`. 


La diferencia principal con las funciones normales es que las funciones de flecha no se pueden nombrar y que una función flecha no tiene su propio `this`; utiliza el valor del contexto de ejecución que la contiene.

```js
class Persona {
	constructor(nombre) {
        this.nombre = nombre;
    }

	esperarEImprimirNombre() {
		setTimeout(() => {
			console.log(this.nombre);
		}, 2000);
  	}
}

var a = new Persona('pepe');
a.esperarEImprimirNombre();
```

Si se usa la sintaxis de función normal, se necesita usar `.bind()`.


## Importar

ES6 permite importar subconjuntos de archivos con la palabra clave import.

```js
// importar todas las funciones de React
import React from 'react';

// solo importa la función calcularPrecio de Tienda
import { calcularPrecio } from 'Tienda';

// importar todas las funciones como un objeto llamado 'utilidades'
import * as utilidades from './utilidades';
``` 

La importación de subconjuntos de archivos hace que la carga de archivos sea mucho más eficiente.


> **Referencias**
>
> - [MDN sobre JavaScript](https://developer.mozilla.org/es/docs/Web/JavaScript)
> - Libro en el aula.
> - Ejemplos en: https://github.com/cbiale/POO2_Javascript