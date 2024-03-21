# Notas sobre Genéricos en Java

## ¿Qué son los Genéricos?

Los genéricos en Java son una característica del lenguaje que permiten escribir código más flexible y seguro. Permiten a las clases, interfaces y métodos operar con tipos de objetos específicos sin necesidad de especificarlos en la definición.

### Ejemplo Básico

```java
List<String> lista = new ArrayList<>();
lista.add("texto");
String s = lista.get(0); // No se necesita casting
```

## ¿Qué Problema Resuelven?

Antes de los genéricos, Java utilizaba colecciones que podían almacenar objetos de cualquier tipo, lo cual llevaba a problemas de tipo en tiempo de ejecución y requería casting explícito de objetos. Los genéricos resuelven estos problemas permitiendo definir una colección con un tipo específico de elementos, lo cual asegura la seguridad del tipo en tiempo de compilación.

### Ejemplo sin Genéricos

```java
List lista = new ArrayList();
lista.add("texto");
String s = (String) lista.get(0); // Necesario casting explícito
```

### Ejemplo con Genéricos

```java
List<String> lista = new ArrayList<>();
lista.add("texto");
String s = lista.get(0); // No se necesita casting
```

## ¿Cómo se Utilizan?

Los genéricos se pueden utilizar en clases, interfaces y métodos. Al declarar una clase o interfaz, se pueden definir uno o más parámetros de tipo que serán reemplazados por tipos concretos cuando se instancie.

### Clases Genéricas

```java
public class Caja<T> {
    private T contenido;

    public void set(T contenido) {
        this.contenido = contenido;
    }

    public T get() {
        return contenido;
    }
}
```

### Uso de Clases Genéricas

```java
Caja<String> cajaDeTexto = new Caja<>();
cajaDeTexto.set("Hola Mundo");
String texto = cajaDeTexto.get();
```

### Métodos Genéricos

Los métodos genéricos permiten especificar uno o más parámetros de tipo solo para ese método, independientemente de la clase donde se declare.

```java
public static <T> void imprimirCaja(Caja<T> caja) {
    System.out.println(caja.get());
}
```

### Comodines en Genéricos

Los comodines (`?`) se utilizan para trabajar con código que opera en tipos genéricos desconocidos.

- `? extends T`: Representa cualquier tipo que sea un subtipo de T.
- `? super T`: Representa cualquier tipo que sea un supertipo de T.

### Ejemplo de Comodines

```java
public void procesarElementos(List<? extends Number> lista) {
    for (Number elemento : lista) {
        // Procesamiento
    }
}
```
