## 5.1. Métodos constructores

Un constructor en Java es un método especial _**utilizado para inicializar objetos de una clase**_. Aquí están algunas de sus características y funcionalidades:

1. **Nombre igual al de la clase:** El nombre de un constructor debe ser idéntico al nombre de la clase a la que pertenece.
2. **No tiene tipo de retorno explícito:** A diferencia de otros métodos, un constructor no tiene un tipo de retorno explícito, ni si quiera void.
3. **Se invoca automáticamente:** El constructor se llama automáticamente cuando se crea una instancia de la clase con la palabra clave **`new`**.
4. **Puede tener parámetros:** Los constructores pueden aceptar parámetros que se utilizan para inicializar los atributos del objeto durante su creación.

Ejemplo de un constructor básico:

```java
public class EjemploClase {
    // Atributos de la clase
    private int valor;

    // Constructor sin parámetros
    public EjemploClase() {
        // Inicialización por defecto
        this.valor = 0;
    }

    // Constructor con parámetro
    public EjemploClase(int valorInicial) {
        // Inicialización con el valor proporcionado
        this.valor = valorInicial;
    }

    // Otros métodos y lógica de la clase
}
```

Al crear una instancia de esta clase, el constructor correspondiente se invocará automáticamente:

```java
EjemploClase objeto1 = new EjemploClase(); // Constructor sin parámetros
EjemploClase objeto2 = new EjemploClase(10); // Constructor con parámetros
```

**Los constructores son esenciales para garantizar que los objetos se inicialicen correctamente y estén en un estado coherente desde el principio.**

### 5.1.1. Método constructor predeterminado

En Java, el constructor predeterminado es un constructor proporcionado automáticamente por el compilador **si una clase no tiene ningún constructor definido explícitamente.** Aquí están sus características y funcionalidades:

1. **Generación automática:** Si una clase no tiene ningún constructor definido, Java genera automáticamente un constructor predeterminado sin parámetros.
2. **Acción implícita:** Este constructor predeterminado se ejecuta implícitamente cuando se crea una instancia de la clase utilizando la palabra clabe **new**.
3. **Inicialización por defecto:** El constructor predeterminado inicializa los campos de la clase con valores predeterminados. Por ejemplo, los tipos numéricos se inicializan a **0**, booleanos a **false** y referencias a **null**.

Ejemplo de una clase con constructor predeterminado:

```java
public class EjemploClase {
    // Atributos de la clase
    private int valor;
    private String texto;

    // Constructor predeterminado generado automáticamente
    public EjemploClase() {
        // Inicialización por defecto
        // this.valor se inicializa a 0
        // this.texto se inicializa a null
    }

    // Otros métodos y lógica de la clase
}
```

Al crear una instancia de esta clase sin proporcionar argumentos, se utiliza el constructor predeterminado:

```java
EjemploClase objeto = new EjemploClase(); // Constructor predeterminado
```

Es importante tener en cuenta que si defines explícitamente al menos un constructor en tu clase, el constructor predeterminado ya no se generará automáticamente, a menos que lo declares explícitamente. En ese caso, deberás proporcionar tanto el constructor predeterminado como cualquier otro constructor que necesites.

### 5.1.2. Sobrecarga de constructores

La soborecarga de constructores en Java se refiere a tener varios contructores en una clase con la misma firma de nombre pero con diferente lista de parámetros. Esto permite a la clase tener flexibilidad al instanciar objetos, ya que los constructores pueden aceptar diferentes combinaciones de argumentos. Aquí están las características y funcionalidades de la sobrecarga de constructores:

1. **Mismo nombre de constructor:** Todos los constructores sobrecargados deben tener el mismo nombre, pero deben diferenciarse por la cantidad, orden o tipos de parámetros.
2. **Diferentes listas de parámetros:** Cada constructor sobrecargado puede tener una lista de parámetros diferente. La combinación única de tipos, orden y cantidad de parámetros define la firma del constructor.
3. **Invocación bassada en los argumentos proporcionados:** Cuando se crea una instancia de la clase utilizando la palabra clave **new**, Java determina automáticamente cuál constructor debe invocarse basándose en los argumentos proporcionados durante la creación del objeto.

Ejemplo de sobrecarga de constructores:

```java
public class EjemploSobrecargaConstructores {
    private int valor;

    // Constructor sin parámetros
    public EjemploSobrecargaConstructores() {
        this.valor = 0;
    }

    // Constructor con un parámetro
    public EjemploSobreCargaConstructores(int valorInicial) {
        this.valor = valorInicial;
    }

    // Constructor con dos parámetros
    public EjemploSobreCargaConstructores(int valorInicial, String mensaje) {
        this.valor = valorInicial;
        System.out.println(mensaje);
    }

    // Otros métpdps y lógica de la clase
}
```

Al crear una instancia de esta clase, puedes elegir qué constructor utilizar según tus necesidades:

```java
EjemploSobrecargaConstructores objeto1 = new EjemploSobrecargaConstructores(); // Constructor sin parámetros
EjemploSobrecargaConstructores objeto2 = new EjemploSobrecargaConstructores(10); // Constructor con un parámetro
EjemploSobrecargaConstructores objeto3 = new EjemploSobrecargaConstructores(10, "¡Hola Mundo!"); // Constructor con dos parámetros
```

**La sobrecarga de constructores proporciona flexibilidad al programador al permitir la creación de objetos de una clase de diferentes maneras, según los requisitos específicos de la aplicación.**

### 5.1.3. Cadena de constructores

La cadena de constructores en Java se refiere al proceso de invocar un constructor desde otro dentro de la misma clase o, en el caso de la herencia, invocar un constructor de la superclase. Esta técnica permite reutilizar código y organizar la inicialización de objetos. Aquí están las características y funcionalidades de la cadena de constructores:

1. **Invocación de otros constructores:** La cadena de constructores implica llamar a otro constructor utilizando la palabra clave **this()** para la misma clase o **super()** para la superclase.
2. **Orden de invocación:** La llamada al constructor debe ser la primera instrucción en el cuerpo del constructor. Esto asegura que la cadena de constructores se utilice para la inicialización antes de que se ejecute cualquier otra lógica en el constructor.
3. **Evitar redundancia de código:** La cadena de constructores ayuda a evitar la duplicación de código al centralizar la lógica común de inicialización en un constructor, que luego puede ser invocado por otros constructores según sea necesario.

Ejemplo de cadena de constructores:

```java
public EjemploConstructorChaining {
    private int valor;
    private String mensaje;

    // Constructor principal iniciando la cadena de constructores
    public EJemploConstructorChaining() {
        // Llamar al segundo constructor
        this(0);
    }

    // Segundo constructor llamando al tercer constructor
    public EjemploConstructorChaining(int valor) {
        // Llamar al tercer constructor
        this(valor, "Mensaje predeterminado");
    }

    // Tercer constructor realizando la inicialización final
    public EjemploConstructorChaining(int valor, String mensaje) {
        // Inicializar variables de instancia
        this.valor = valor;
        this.mensaje = mensaje;
    }

    // Otros métodos y lógica de la clase
}
```

Al crear una instancia de esta clase, la cadena de constructores permite que se utilice el constructor principal y las llamadas subsecuentes a otros constructores se realizan automáticamente según la jerarquía de invocación.

```java
EjemploConstructorChaining objeto = new EjemploConstructorChaining();
```

**La cadena de constructores es una técnica eficiente para estructurar el código de inicialización en las clases de Java, facilitando la reutilización y el mantenimiento del código.**
