# 13.1 Abstracción

La abstracción es uno de los cuatro pilares fundamentales de la Programación Orientada a Objetos (POO), junto con la encapsulación, la herencia y el polimorfismo. La abstracción se trata de ocultar los detalles complejos y mostrar solo las características esenciales de un objeto o sistema. En esencia, permite al desarrollador centrarse en lo que hace un objeto sin necesidad de conocer cómo lo logra.

## 13.1.2. Cómo funciona la abstracción

La abstracción se puede implementar de dos manera principales en la POO:

1.- **Clases Abstractas**: Una clase declarada como abstracta no puede ser instanciada directamente, y está destinada a ser subclaseada por otras clases. Puede contener métodos abstractos (sin implementación) que pueden ser implementados por las subclases, así como métodos con implementación completa.

2.- **Interfaces**: Una interfaz es un contrato que define un conjunto de métodos sin implementaciones. Las clases que implementar una interfaz deben proporcionar implementaciones para todos los métodos definidos en la interfaz.

Ambas, clases abstractas e interfaces, se utilizan para definir un nivel alto de abstracción, dejando los detalles de implementación a las clases concretas que heredan la clase abstracta o implementan la interfaz.

## 13.1.3. Clases Abstractas vs Interfaces

La elección para utilizar una interfaz o una clase abstracta para implementar la abstracción en Java depende de varios factores relacionados con el diseño de tu aplicación. A continuación se presentan algunas pautas generales para decidir cuál es la mejor opción en diferentes contextos:

**Utiliza una Interfaz cuando**:

- **Esperas que clases no relacionadas implementen tu interfaz.** Las interfaces son ideales para definir un contrato común para clases que no comparten una jerarquía de herencia.
- **Quieres aprovechar la herencia múltiple de tipo.** Java no permite la herencia múltiple de clases, pero una clase puede implementar múltiples interfaces, lo que permite a los objetos heredar varios comportamientos de interfaz.

**Utiliza una Clase Abstracta cuando**:

- **Estado compartido.** Las clases abstractas pueden tener campos de estado, permitiendo compartir no solo comportamiento (métodos), sino también datos (estado) entre varias subclases. Las interfaces no pueden tener campos de estado que no sean static y final.
- **Métodos Constructores y Destructores:** Las clases abstractas pueden definir constructores y destructores, lo cual es útil para inicializar correctamente cualquier estado necesario antes de que un objeto se utilice o para limpiar recursos antes de que el objeto se destruya. Las interfaces no pueden tener constructores.
- **Acceso más Restrictivo para Métodos:** Las clases abstractas permiten definir métodos con diferentes niveles de acceso (private, protected, public), mientras que los métodos en las interfaces son públicamente accesibles (aunque los métodos private fueron introducidos en interfaces en Java 9, su uso es más limitado comparado con las clases).

## 13.1.4. Ejemplo en código Java

Supongamos que estamos desarrollando un sistema para gestionar vehículos en un juego. Todos los vehículos deben ser capaces de acelerar y frenar, pero la manera exacta en que estos comportamientos se llevan a cabo varía según el tipo de vehículo.

Primero, definimos una interfaz '**Vehículo**' que declare los métodos '**acelerar**' y '**frenar**'.

```java
public interface Vehiculo {
  void acelerar();
  void frenar();
}
```

Luego, implementamos esta interfaz en clases concretas que representan diferentes tipos de vehículos, como un '**Coche**' y una '**Motocicleta**'.

```java
public class Coche implements Vehiculo {
  @Override
  public void acelerar() {
    System.out.println("El coche acelera suavemente.");
  }

  @Override
  public void frenar() {
    System.out.println("El coche frena con los frenos de disco.");
  }
}

public class Motocicleta implements Vehiculo {
  @Override
  public void acelerar() {
    System.out.println("El motocicleta acelera rápidamente.");
  }

  @Override
  public void frenar() {
    System.out.println("La motocicleta frena con los discos de tambor.");
  }
}
```

Finalmente, podemos usar estas clases a través de la abstracción proporcionada por la interfaz '**Vehiculo**' sin preocuparnos por los detalles específicos de cómo cada vehículo acelera o frena.

```java
public class Main {
  public static void main(String[] args) {
    Vehiculo miCoche = new Coche();
    Vehiculo miMotocicleta = new Motocicleta();

    miCoche.acelerar();
    miMotocicleta.acelerar();

    miCoche.frenar();
    miMotocicleta.frenar();
  }
}
```
