# 12.1 Polimorfismo

El polimorfismo en programación orientada a objetos (POO) se refiere a la capacidad de objetos de diferentes clases de responder al mismo mensaje de manera distinta. Esto permite que un mismo método pueda comportarse de manera diferente según el objeto que lo recibe.

## 12.2. Características

1.- Permite el uso de un mismo nombre para métodos en diferentes clases.

2.- Ayuda a mejorar la flexibilidad y reutilización del código.

3.- Facilita la implementación de interfaces y herencia.

## 12.3. Funcionalidades

1.- Polimorfismo de sobrecarga: Ocurre cuando una clase tiene múltiples métodos con el mismo nombre pero con diferentes parámetros.

2.- Polimorfismo de sobrescritura: Sucede cuando una subclase redefine un método de su superclase para proporcionar una implementación específica.

## 12.4. Ejemplo

```java
class Animal {
    public void hacerSonido() {
        System.out.println("Haciendo sonido genérico...");
    }
}

class Perro extends Animal {
    @Override
    public void hacerSonido() {
        System.out.println("Guau guau");
    }
}

class Gato extends Animal {
    @Override
    public void hacerSonido() {
        System.out.println("Miau");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal animal1 = new Perro();
        Animal animal2 = new Gato();

        animal1.hacerSonido(); // Output: Guau guau
        animal2.hacerSonido(); // Output: Miau
    }
}

```

En este ejemplo, tanto la clase **Perro** como la clase **Gato** heredan de la clae **Animal** y sobrescriben el método **hacerSonido()**. Al llamar al método **hacerSonido()** en los objetos **animal1** y **animal2**, el resultado es diferente dependiendo del tipo de animal, lo que ejemplifica el polimorfismo en acción.
