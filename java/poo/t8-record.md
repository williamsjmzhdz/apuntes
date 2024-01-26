# 8.1 Record

Un record en Java es una nueva forma de definir clases que están diseñadas principalmente para almacenar datos de manera inmutable. Está destinado a ser utilizado cuando se necesita un objeto simple para representar datos y no tiene comportamiento adicional más allá de la lectura y escritura de esos datos.

## 8.1.1. Características

- **Inmutabilidad:**

  - Todos los campos de un record son automáticamente **final** e **immutable**, lo que significa que una vez que se han establecido sus valores en el constructor, no pueden cambiar.

- **Métodos de acceso:**

  - Los records generan automáticamente métodos de acceso (**getters**) para todos sus campos. También generan automáticamente un método **toString**, **hashCode** y **equals** basados en todos los campos de la clase.

- **Constructor:**

  - Se proporciona un constructor implícito que toma todos los campos como argumentos y los inicializa. No es necesario escribir un constructor explícito, pero puedes hacerlo si necesitar realizar alguna lógica adicional.

- **Sintaxis concisa**
  - La sintaxis para definir un record es más concisa que la de una clase convencional. Se puede definir un record en una sola línea.

## 8.1.2. Ejemplo

```java
record Persona(String nombre, int edad) {
    // No es necesario escribir métodos, el compilador los genera automáticamente
}

// Uso del record
Persona persona = new Persona("Juan", 25);
System.out.println(persona.nombre()); // Acceso al campo nombre
System.out.println(persona);          // Método toString generado automáticamente

```

## 8.1.3. Funcionalidades adicionales

- **Patrón de desestructuración**

  - Los records permiten desestructuración en expresiones lambda y expresiones switch, lo que facilita el manejo de datos.

- **Herencia e Interfaces**
  - Los records pueden extender otras clases y también implementar interfaces. En este caso, heredan automáticamente los métodos de la clase padre y de las interfaces.

Los records son especialmente útiles cuando se trata de modelar datos simples y reducir la cantidad de código boilerplate asociado con las clases de datos. Simplifican la creación de clases inmutables, promoviendo buenas prácticas de diseño y facilitando el mantenimiento del código.
