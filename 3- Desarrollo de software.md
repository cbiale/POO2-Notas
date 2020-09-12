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

## ¿Dónde están los problemas "reales"?

# Especificación de requisitos de software

## El documento de especificaciones

## Mejores prácticas

# Wireframe

# Modelos de procesos de software

## ¿Ágil o no ágil?

## ¿Qué es (y no) desarrollo incremental?

## En la materia

