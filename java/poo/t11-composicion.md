# 11.1. Composición

La composición en programación orientada a objetos (POO) es un concepto fundamental que permite construir objetos complejos combinando otros objetos más simples. En este enfoque, un objeto se compone de uno o más objetos de otros tipos, en lugar de heredar su funcionalidad. La composición se basa en la idea de que los objetos pueden contener referencias a otros objetos como parte de su estructura interna.

## 11.1.2. Características

- **Reutilización de código:** Permite reutilizar objetos existentes al componerlos en otros objetos nuevos.
- **Modularidad:** Facilita la construcción de sistemas complejos diviéndolos en componentes más pequeños y manejables.
- **Flexibilidad:** Los objetos pueden ser cambiados o actualizados fácilmente sin afectar a otros componentes del sistema.

## 11.1.3. Funcionalidades

- **Creación de objetos compuestos:** Se pueden crear objetos combinando varios objetos simples.
- **Establecimiento de relaciones:** Los objetos pueden tener relaciones de uno a uno, uno a muchos o muchos a muchos, dependiendo de cómo se compongan.
- **Acceso a funcionalidades:** Los objetos pueden acceder a las funcionalidades de los objetos que componen.

## 11.1.4. Ejemplo

```java
class Libro {
  private String titulo;
  private String autor;

  public Libro(String titulo, String autor) {
    this.titulo = titulo;
    this.autor = autor;
  }

  // Getters y setters
  public String getTitulo() {
    return titulo;
  }

  public String getAutor() {
    return autor;
  }

  public void setTitulo(String titulo) {
    this.titulo = titulo;
  }

  public void setAutor(String autor) {
    this.autor = autor;
  }
}

import java.util.ArrayList;
import java.util.List;

class Biblioteca {
  private List<Libro> libros;

  public Biblioteca() {
    this.libros = new ArrayList<>();
  }

  // Agregar libro a biblioteca
  public void agregarLibro(Libro libro) {
    libros.add(libro)
  }

  // Buscar libro por titulo
  public Libro buscarLibroPorTitulo(String titulo) {

    for (Libro libro : libros) {
      if (libro.getTitulo().equals(titulo)) {
        return libro;
      }
    }

    return null;
  }
}
```

En este ejemplo, la clase **Biblioteca** utiliza la composición con la clase **Libro**. La clase **Biblioteca** contiene una lista de objetos **Libro**, lo que permite agregar libros a la biblioteca y buscar libros por título sin la necesidad de heredar de la clase **Libros**.
