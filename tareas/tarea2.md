# Tarea 2

## Introducción

Vamos a crear la base de datos de nuestro proyecto, para ello ingresamos en `psql`:

```shell
sudo -u postgres psql
```

Creamos la base de datos `revisiones`:

```
postgres=# create database revisiones;
```

Cambiamos a la base de datos recientemente creada:

```
postgres=# \c revisiones;
```

creamos las tablas para `Revision` y `Curso`:

```
revisiones=# CREATE TABLE cursos (id SERIAL PRIMARY KEY, nombre VARCHAR NOT NULL);
```

```
revisiones=# CREATE TABLE revisiones (id SERIAL, calificacion INT NOT NULL, comentario VARCHAR NOT NULL, consejo VARCHAR NOT NULL, curso_id INT NOT NULL REFERENCES cursos(id));
```

## Desarrollo

1. Modifiquen el proyecto para poder acceder a la base de datos usando `sql2o`.
2. Prueben la funcionalidad de los cambios realizados.

> Para completar la tarea realicen la lectura 6.

