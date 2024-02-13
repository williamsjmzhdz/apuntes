# 9.1. Encapsulamiento

El encapsulamiento es un concepto fundamental en programación orientada a objetos que se refiere a la capacidad de ocultar los detalles internos de un objeto y exponer solo lo necesario para interactuar con él. En esencia, encapsular un objeto significa agrupar sus atributos y métodos en una única unidad coherente.

## 9.1.2. Características

- **Ocultamiento de la implmentación**

  - Los detalles internos de un objeto están ocultos fuera de su definición, lo que previene que otros objetos accedan directamente a ellos.

- **Acceso controlado**

  - Se establece un nivel de acceso para cada atributo y método, permitiendo que solo ciertas partes del programa puedan manipularlos.

- **Modularidad**
  - Al encapsular atributos y métodos juntos, se promueve una estructura modular que facilita la organización y mantenimiento del código

## 9.1.3. Funcionalidades

- **Mejora la seguridad**

  - AL restringer el acceso a los datos internos, se reduce el riesgo de manipulación indebida.

- **Mejora la modularidad**

  - Los objetos encapsulados son unidades independientes que pueden ser modificadas y mantenidas de forma aislada, lo que facilita el desarrollo de software modular y reutilizable.

- **Abstracción**
  - Al exponer solo una interfaz pública para interactuar con un objeto, se promueve la abstracción y se simplifica la complejidad del sistema.

## 9.1.4. Ejemplo

```java
public class CuentaBancaria {
  private String titular;
  private double saldo;

  public CuentaBancaria(String titular, double saldo) {
    this.titular = titular;
    this.saldo = saldo;
  }

  public double getSaldo() {
    return saldo;
  }

  public void depositar(double cantidad) {
    if (cantidad > 0) {
      saldo += cantidad;
    } else {
      System.out.println("Error: la cantidad debe ser mayor que cero.");
    }
  }

  public void retirar(double cantidad) {
    if (cantidad > 0 && cantidad <= saldo) {
      saldo -= cantidad;
    } else {
      System.out.prinln("Error: Fondos insuficientes o cantidad invalida.");
    }
  }

  public void mostrarInformacion() {
    System.out.println("Titular: " + titular);
    System.out.println("Saldo actual: " + saldo);
  }
}


```

En este código encapsula los detalles internos de la implementación de una cuenta bancaria y expone métodos públicos para acceder y modificar el saldo (getSaldo(), depositar(), retirar()) y para mostrar la información de la cuenta (mostrarInformacion()). Los detalles de implementación, como la verificación de fondos suficientes al retirar dinero, están ocultos dentro de la clase, lo que promueve la modularidad y la abstracción en el diseño del código.
