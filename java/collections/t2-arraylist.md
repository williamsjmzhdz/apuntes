# 2. ArrayList

**ArrayList** es una implementación de la interfaz **List** que utiliza un arreglo dinámico para almacenar los elementos insertados en la lista. A diferencia de un arreglo estándar, **ArrayList** puede cambiar su tamaño en tiempo de ejecución, ofreciendo flexibilidad adicional.

## 2.1. Características principales

- **Tamaño dinámico:** A diferencia de los arreglos estáticos, **ArrayList** se expande automáticamente cuando se agregan más elementos de los que puede contener.

- **Acceso aleatorio:** Permite el acceso aleatorio a cualquier elemento por su índice, ofreciendo operaciones de lectura eficientes.

- **Implementa List:** Hereda métodos de la interfaz **List**, como **add**, **remove**, **indexOf**, entre otros, permitiendo una manipulación flexible de los elementos.

## 2.2. Ventajas de usar ArrayList

- **Facilidad de uso:** Su API es intuitiva y facilita la manipulación de colecciones de objetos.

- **Rendimiento en accesos aleatorios:** Ideal para escenarios donde predominan las lecturas de datos.

- **Interoperabilidad:** Como parte del framework de Collections, interactúa sin problemas con otras estructuras de datos de Java.

## 2.3. Consideraciones

- **Capacidad vs Tamaño:** La capacidad de un **ArrayList** es el tamaño del arreglo usado para almacenar los elementos de la lista, mientras que su tamaño es el número de elementos actualmente en la lista.

- **Rendimiento en inserciones y eliminaciones:** Puede ser menos eficiente en operaciones que modifican la lista, especialmente en los elementos del principio, debido al desplazamiento necesario de los elementos.

## 2.4. Ejemplo básico de uso

```java
import java.util.ArrayList;

public class EjemploArrayList {
    public static void main(String[] args) {
        ArrayList<String> listaDeNombres = new ArrayList<>();

        // Agregar elementos
        listaDeNombres.add("Alice");
        listaDeNombres.add("Bob");
        listaDeNombres.add("Charlie");

        // Acceder a un elemento
        System.out.println("El segundo nombre es: " + listaDeNombres.get(1));

        // Eliminar un elemento
        listaDeNombres.remove("Alice");

        // Recorrer la lista
        for(String nombre : listaDeNombres) {
            System.out.println(nombre);
        }
    }
}

```

En este ejemplo, se demuestra cómo crear una instancia de **ArrayList**, agregar elementos, acceder a ellos, eliminarlos y recorrer la lista.

## 2.5. Conclusión

**ArrayList** es una herramienta poderosa y flexible en el arsenal de cualquier desarrollador Java, ofreciendo una combinación equilibrada de facilidad de uso y rendimiento para la manipulación de colecciones de objetos.
