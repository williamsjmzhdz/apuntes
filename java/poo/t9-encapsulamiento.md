# 9.1. Encapsulamiento

El encapsulamiento es uno de los cuatro principios fundamentales de la programación orientada a objetos (OOP), junto con la herencia, el polimorfismo y la abstracción. En Java el encapsulamiento se refiere a la práctica de ocultar los detalles internos de una clase y proporcionar una interfaz bien definida para interacturar con esa clase.

## 9.1.2. Características

- **Acceso controlado**

  - El encapsulamiento se logra mediante el control de acceso a los miembros de una clase (atributos y métodos). Los modificadores de acceso como **public**, **private**, y **protected** se utilizan para limitar el acceso.

- **Ocultamiento de detalles internos**

  - Los detalles internos de la implementación de una clase se ocultan a otras clases. Solo se exponen los métodos y atributos necesarios para utilizar la funcionalidad de la clase.

- **Mantenimiento y evolución**
  - El encapsulamiento facilita el mantenimiento del código ya que los cambios internos en la implementación de una clase no afecta directamente a las clases que la utilizan, siempre y cuando la interfaz pública permanezca inalterada.

## 9.1.3. Funcionalidades

- **Métodos de acceso (getters y setters)**

  - Se utilizan métodos de acceso (**getters** y **setters**) para permitir el acceso controlado a los atributos de una clase. Esto evita la manipulación directa de los datos y permite establecer restricciones en la modificación de los valores.

- **Modificadores de acceso**
  - Los modificadores **public**, **private** y **protected** se utilizan para controlar la visibilidad de las clases, métodos y atributos. Por ejemplo, hacer una atributo **private** significa que solo se puede acceder a él desde dentro de la propia clase.

## 9.1.4. Ejemplo

```java
public class CuentaBancaria {
    private String titular;
    private double saldo;

    // Constructor
    public CuentaBancaria(String titular, double saldo) {
        this.titular = titular;
        this.saldo = saldo;
    }

    // Getter para el titular
    public String getTitular() {
        return titular;
    }

    // Getter para el saldo
    public double getSaldo() {
        return saldo;
    }

    // Setter para el saldo
    public void setSaldo(double nuevoSaldo) {
        if (nuevoSaldo  ) {
            this.saldo = nuevoSaldo;
        } else {
            System.out.println("El saldo no puede ser negativo.");
        }
    }
}

// Uso de la encapsulación
public class Main {
    public static void main(String[] args) {
        CuentaBancaria cuenta = new CuentaBancaria("Juan Perez", 1000.0);

        // Acceso controlado a través de getters y setters
        System.out.println("Titular: " + cuenta.getTitular());
        System.out.println("Saldo: " + cuenta.getSaldo());

        // Modificación controlada del saldo
        cuenta.setSaldo(1500.0);
        System.out.println("Nuevo Saldo: " + cuenta.getSaldo());
    }
}

```

En este ejemplo, la clase **CuentaBancaria** encapsula los detalles internos (**titular** y **saldo**) y proporciona métodos de acceso controlado para interactuar con esos atributos. El encapsulamiento asegura que el saldo no pueda ser modificado directamente de una manera no deseada y que el acceso a los detalles internos esté bien definido.
