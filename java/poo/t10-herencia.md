# 10.1. Herencia

La herencia es un concepto que permite la creación de clases nuevas basadas en clases existentes, aprovechando y extendiendo sus características. En este contexto, a la clase existente se le conoce como clase base o clase padre, y la nueva clase se denomina clase derivada o clase hija.

## 10.1.1. Características

- **Reutilización de código:** Permite utilizar y extender la funcionalidad de una clase existente en lugar de escribir código desde cero.

- **Jerarquía:** Se establece una relación jerárquica entre las clases, donde la clase hija hereda propiedades y métodos de la clase padre.

- **Extensión y especialización:** La clase hija puede añadir nuevos atributos o métodos, así como sobrescribir o especializar los existentes.

## 10.1.2. Funcionalidades

- **Acceso a miembros de la clase padre:** La clase hija puede acceder a los miembros (atributos y métodos) de la clase padre, dependiendo de su nivel de acceso (público, protegido o privado).

- **Polimorfismo:** Permite tratar objetos de la clase hija como si fueran objetos de la clase padre, facilitando la flexibilidad en el diseño y la manipulación de objetos.

## 10.1.3. Ejemplo práctico

```java
// Clase base o padre
class Animal {
  String nombre;

  Animal(String nombre) {
    this.nombre = nombre;
  }

  void hacerSonido() {
    System.out.println("Haciendo sonido genérico")ñ
  }
}

// Clase derivada o hija
class Perro extends Animal {
  Perro(String nombre) {
    // Llama al constructor de la clase padre
    super(nombre);
  }

  // Sobrescribe el método hacerSonido() de la clase padre
  @Override
  void hacerSonido() {
     System.out.println("Guau guau");
  }

  // Método específico de la clase perro
  void perseguirCola() {
    System.out.println("Persiguiendo la cola");
  }
}

// Uso de las clases
public class Main {
    public static void main(String[] args) {
        // Crear un objeto de la clase Perro
        Perro miPerro = new Perro("Firulais");

        // Acceder a miembros de la clase base
        System.out.println("Nombre del animal: " + miPerro.nombre);

        // Llamar al método de la clase derivada
        miPerro.hacerSonido(); // Imprime "Guau guau"

        // Llamar al método específico de la clase Perro
        miPerro.perseguirCola(); // Imprime "Persiguiendo la cola"
    }
}
```

En este ejemplo, la clase **Perro** hereda de la clase **Animal**. La clase **Perro** extiende la funcionalidad al sobrescribir el método **hacerSonido** y añadir un nuevo método **perseguirCola**. La instancia de la clase **Perro** puede ser tratada como un objeto de la clase **Animal**, demostrando así la herencia en acción.
