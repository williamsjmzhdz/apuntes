# 1. Collections

El framework de Collections en Java proporciona una arquitectura unificada para almacenar y manipular grupos de objetos. Los collections permiten operaciones tales como la búsqueda, la inserción, la eliminación y la manipulación de datos. Java Collections pueden clasificarse en varias interfaces, cada una con sus propias características.

## 1.1. Interfaces principales del framework Collections

- **Collection:** La raíz de la jerarquía de colecciones. Define operaciones básicas como **add**, **remove** y **clear**.
- **List:** Una colección ordenada que puede contener elementos duplicados. Permiten acceso posicional a los elementos. Ejemplos incluyen **ArrayList** y **LinkedList**.

- **Set:** Una colección que no permite elementos duplicados. Ejemplos son **HashSet** y **TreeSet**.

- **Queue:** Una colección diseñada para operaciones de espera. Los elementos se procesan en orden FIFO (primero en entrar, primero en salir) o según prioridades. Ejemplo: **PriorityQueue**.

- **Map:** Objeto que asocia claves a valores, no siendo una colección verdadera, pero integrada con el framework. Ejemeplos incluyen **HashMap** y **TreeMap**.

## 1.2. Ventajas del uso de Collections

- **Reducción de esfuerzo de programación:** Al proporcionar estructuras de datos y algoritmos comunes, el framework de Collections reduce la necesidad de implementar estas estructuras manualmente.

- **Aumento de calidad:** Las Collections están diseñadas para ser de alta calidad y rendimiento, mejorando la confiabilidad del software.

## 1.3. Ejemplo básico de uso

```java
import java.util.ArrayList;
import java.util.List;

public class EjemeploCollections {
  public static void main(String[] args) {
    // Crear una colección de tipo List para almacenar strings
    List<String> frutas = new ArrayList<>();
    frutas.add("Banana");
    frutas.add("Manzana");
    frutas.add("Fresa");

    // Recorrer y mostrar los elementos
    for(String fruta : frutas) {
      System.out.println(fruta);
    }
  }
}
```

En este ejemplo, se crea una instancia de **ArrayList** que implementa la interfaz **List**, se agregan elementos a ella y luego se recorren estos elementos para mostrarlos.

## 1.4. Conclución

EL framework de Collections es un componente esencial en Java, que proporciona estructuras de datos potentes y flexibles. Su comprensión y uso adecuado es fundamental para cualquier desarrollador Java para crear aplicaciones eficientes y mantenibles.
