# Lectura 6 - Sql2o

Para conectarse a una base de datos deben crear un objeto sql2o de la siguiente forma:

```java
var sql2o = new Sql2o("jdbc:postgresql://localhost:PUERTO/DB", "USUARIO", "CLAVE");
```

> Adapten los datos a sus necesidades. Deben tener la biblioteca de JDBC para PostgreSQL y de sql2o.

El repositorio de una clase debe contener un atributo como el siguiente: 

```
private final Sql2o sql2o;
```

Y el constructor del repositorio debe recibir un objeto al cual asignarle a su atributo:

```
    public Sql2oCursosRepositorio(Sql2o sql2o) {
        this.sql2o = sql2o;
    }
```

Ahora si, puede crear los repositorios y trabajar con ellos.
