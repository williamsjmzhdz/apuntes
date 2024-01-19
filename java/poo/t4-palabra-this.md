## 4.1. Palabra reservada "this"

La palabra reservada "this" en Java se refiere a una referencia al objeto actual en el cual se está ejecutando el código. Tiene varias funcionalidaes y características.

1. **Referencia al objeto actual:** Cuando se utiliza dentro de un método o constructor, "this" hace referencia al objeto actual en el que se está ejecutando el código.

2. **Evita ambigüedades:** En situaciones donde hay variables locales con el mismo nombre que los campos de la clase, se utiliza "this" para referirse al campo de la clase y evitar ambigüedades.

```java
public class Ejemplo {
    private int x;

    public void setX(int x) {
        this.x = x; // "this" se utiliza para referirse al campo de la clase
    }
}

```

3. **Invocación de constructor:** Se puede utilizar "this" para llamar a otro constructor de la misma clase. Esto se utiliza en la construcción de constructores sobrecargados.

```java
public class Ejemplo {
    private int x;

    public Ejemplo() {
        this(0); // Llama al constructor con un parámetro
    }

    public Ejemplo(int x) {
        this.x = x;
    }
}

```
