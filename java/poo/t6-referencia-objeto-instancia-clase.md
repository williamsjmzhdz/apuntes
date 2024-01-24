## 6.1. Referencia vs Objeto vs Instancia vs Clase

### 6.1.1. Clase

- **Definición:** Una clase en Java es un plano o plantilla para crear objetos. Se define como un conjunto de atributos (campos) y métodos que los objetos creados a partir de la clase tendrán.
- **Propósito:** Las clases proveen una forma de modelar entidades del mundo real y definir su comportamiento. Encapsulan datos y métodos que operan sobre dichos datos.

### 6.1.2. Objeto

- **Definición:** Un objeto es una instancia de una clase. Es una realización concreta del plano definido por la clase, y representa una entidad específica en el programa.
- **Propósito:** Los objetos encapsulan el estado y comportamiento. Te permiten trabajar con instancias concretas de una clase, cada una teniendo su propio conjunto de datos (atributos) y comportamientos (métodos).

### 6.1.3. Instancia

- **Definición:** En el contexto de Java, "instancia" es a menudo utilizado intercambiablemente con "objeto". Una instancia de una clase es una ocurrencia específica o realización de esa clase, creada utilizando la palabra reservada **"new"**
- **Propósito:** Las instancias representan entidades únicas en tu programa basadas en la definición de una clase. Te permiten trabajar con datos y comportamientos específicos definidos por la clase.

### 6.1.4. Referencia

- **Definición:** Una referencia es una variable que almacena la dirección de memoria (referencia) de un objeto. No almacena el objeto persé, sino que apunta a su locación en memoria.
- **Propósito:** Las referencias son utilizadas para interactuar con objetos. Caando creas un objeto, una variable de referencia es utilizada para acceder y manipular dicho objeto. Múltiples referencias pueden apuntar al mismo objeto en memoria.

Vamos a ilustrar estos conceptos con un ejemplo:

```java
// Class definition
class Car {
  // Attributes
  String brand;
  int year;

  // Constructor
  public Car(String brand, int year) {
    this.brand = brand;
    this.year = year;
  }

  // Method
  public void start() {
    System.out.println("The " + year + " " + brand + " is starting.");
  }
}

// Creating instances (objects) of the class Car
Car car1 = new Car("Toyota", 2022);
Car car2 = new Car("Honda", 2021);

// References to objects
Car reference1 = car1; // reference1 points to the same object as car1
Car reference2 = car2; // reference2 points to the same object as car2

// Using objects and references
car1.start(); // Invoking the start() method on car1
reference2.start(); // Invoking the start() method on car2 pointed to by the reference2
```

En este ejemplo:

- Car is la clase que define el plano para carros.
- car1 y car2 son referencias a los objetos (instancias) de la clase Car en memoria.
- reference1 y reference2 son referencias apuntando a objetos específicos en memoria.
