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

## Extra: Métodos

`ArrayList` en Java ofrece una amplia gama de métodos para manipular listas de objetos. Aquí destacaré algunos de los métodos más utilizados y principales de `ArrayList`, proporcionando una base sólida para su manipulación efectiva:

### Métodos de Modificación

- **`add(E e)`**: Añade el elemento `e` al final de la lista.
- **`add(int index, E element)`**: Inserta el elemento `element` en la posición `index` especificada, desplazando los elementos actuales a la derecha.
- **`remove(Object o)`**: Elimina la primera ocurrencia del objeto `o` de la lista, si está presente.
- **`remove(int index)`**: Elimina el elemento en la posición `index`.
- **`set(int index, E element)`**: Reemplaza el elemento en la posición `index` con `element`.

### Métodos de Consulta

- **`get(int index)`**: Devuelve el elemento ubicado en la posición `index`.
- **`indexOf(Object o)`**: Devuelve el índice de la primera ocurrencia del objeto `o` en la lista, o -1 si la lista no contiene el objeto.
- **`size()`**: Devuelve el número de elementos en la lista.
- **`isEmpty()`**: Devuelve `true` si la lista no contiene elementos.

### Métodos de Iteración

- **`iterator()`**: Devuelve un iterador sobre los elementos en la lista en la secuencia correcta.
- **`listIterator()`**: Devuelve un iterador de lista sobre los elementos en la lista en la secuencia correcta.

### Métodos de Búsqueda

- **`contains(Object o)`**: Devuelve `true` si la lista contiene el objeto `o`.

### Métodos de Operaciones en Rango

- **`subList(int fromIndex, int toIndex)`**: Devuelve una vista de la porción de la lista entre `fromIndex`, inclusive, y `toIndex`, exclusivo.

### Métodos de Conversión

- **`toArray()`**: Devuelve un arreglo que contiene todos los elementos en la lista en la secuencia correcta.

### Métodos de Utilidad

- **`clear()`**: Elimina todos los elementos de la lista.
- **`clone()`**: Devuelve una copia superficial de la lista.
- **`ensureCapacity(int minCapacity)`**: Aumenta la capacidad de la instancia de `ArrayList`, si es necesario, para asegurar que pueda albergar al menos el número de elementos especificado por `minCapacity`.

Estos métodos constituyen la esencia de la manipulación y consulta de `ArrayList` en Java, ofreciendo una flexibilidad considerable para el manejo de colecciones de objetos.
