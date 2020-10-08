# Base de datos

## Mapeo objeto relacional (ORM)

El mapeo objeto relacional *(ORM)* es una aplicación *(biblioteca)* para mapear sus objetos a una base de datos relacional; normalmente, usted describe qué clases y propiedades en el código se asignan a qué tablas y columnas en la base de datos, y luego la biblioteca hace todo el copiado y la traducción. 

> ORM se encuentra entre JDBC y el resto de la aplicación Java.

## Sql2o

**Sql2o** es una pequeña biblioteca de Java, con el propósito de facilitar la interacción con la base de datos. Para usar Sql2o, deben agregarlo como una dependencia a su proyecto.

> Búsquenlo en Maven 

## Ejemplos de uso

Definimos una interfaz para el repositorio o DAO:

```java
public interface CursoRepositorio {
    void agregar(Curso curso) throws RepositorioExcepcion;
    List<Curso> listar();
}
```

Preguntas: 
- Usando un repositorio o DAO, porque conviene definir una interfaz.
- Faltan métodos?

Implementamos la interzas:

```java
public class Sql2oCursoRepositorio implements CursoRepositorio {

    private final Sql2o sql2o;

    public Sql2oCursoRepositorio(Sql2o sql2o) {
        this.sql2o = sql2o;
    }

    @Override
    public void agregar(Curso curso) throws RepositorioExcepcion {

    }

    @Override
    public List<Curso> listar() {
        return null;
    }
}
```

Cuando se usa un objeto sql2o conviene usarlo de la siguiente forma:

```java
try(Connection con = sql2o.open()) {
    // realizar algo en la base de datos.
} catch (Sql2oException ex) {
    // manejar excepciones
}
```

Una declaración **try-with-resources**, es una construcción que asegura que el recurso se cierra al final de la declaración.

Un ejemplo de agregar:

```java
@Override
public void agregar(Curso curso) throws RepositorioExcepcion {
    try (Connection conn = sql2o.open()) {
        String sql = "INSERT INTO Cursos (nombre) VALUES (:nombre);";
        int id = (int) conn.createQuery(sql)
            .bind(curso)
            .executeUpdate()
            .getKey();
        curso.setId(id);
    } catch (Sql2oException ex) {
        throw new CursoExcepcion("No se puede agregar un curso.", ex);
    }
}
```


> **Importante**
> 
> Para que la vinculación funcione sin problemas, debe tener el mismo nombre para los campos en el objeto y los nombres de columna en su tabla

 Un ejemplo de listar:

```java
@Override
public List<Curso> listar() {
    try (Connection conn = sql2o.open()) {
        String sql = "SELECT * FROM Cursos;";
        return conn.createQuery(sql).executeAndFetch(Curso.class);
    }
}
```

> **Tarea**
> 
> Agregar persistencia al proyecto.

