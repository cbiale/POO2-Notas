# Heroku

> Se requiere tener una cuenta en Heroku. 

En primer lugar debemos instalar el cli de [heroku](https://devcenter.heroku.com/articles/heroku-cli#download-and-install).

En Linux solo debemos ejecutar:

```shell
sudo snap install --classic heroku
```

> Instalar `snap` de ser necesario 

Para verificar si la instalación fue correcta ejecutamos: 

```
heroku --version
```

Esto nos devuelve la versión instalada de herocku cli.

El siguiente paso es realizar un login usando:

```
heroku login
```

Luego se debe realizar un login para poder usar docker:

```
heroku container:login
```

Creamos una aplicación usando el comando:

```
heroku create APP
```

> APP es el nombre de nuestra aplicación.

En este ejemplo, vamos a hacer una aplicación en nodejs usando como servidor a express:

```
mkdir servidor
cd servidor
npm init -y
npm install -S express
```

Ahora creamos un archivo index.js con el siguiente contenido

```
const express = require('express')
const app = express()
const port = process.env.PORT


app.get('/', (req, res) => res.send('Hola mundo'))

app.listen(port, () => console.log(port))
```

Ahora vamos a realizar el `Dockerfile` para ubicar la aplicación en un contenedor.

```
FROM node:10-alpine
WORKDIR /app
COPY package.json .
RUN npm install
COPY index.js .
CMD ["node", "index.js"]
```

Indicamos que vamos a usar la imagen de `node:10-apline`, creamos un directorio de trabajo `app`, copiamos nuestro `package.json` y ejecutamos el comando `npm install` para instalar las dependencias, luego copiamos nuestro archivo `index.js` y al final especificamos que se debe ejecutar al iniciar el contenedor.

Luego creamos nuestra imagen ejecutando el siguiente comando:

```
heroku container:push web -a APP
```
> APP es el nombre de la aplicacion que hemos creado con el comando `heroku create`.

Este comando creará nuestra imagen ejecutando el comando `docker build` de manera local. 

Para subir el contenedor a heroku debemos ejecutar:

```
heroku container:release web -a APP
```

Para finalizar, debemos ir a la dirección web de nuestra aplicación para ver nuestra aplicación funcionando.



