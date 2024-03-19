# 3. LinkedList

`LinkedList` en Java es una implementación de la interfaz `List` que emplea una estructura de datos de lista doblemente enlazada, optimizando las operaciones de inserción y eliminación.

## 3.1. Características

### 3.1.1. Lista Doblemente Enlazada

Posee nodos que contienen datos y dos referencias a los nodos vecinos, facilitando la navegación bidireccional.

### 3.1.2. Flexibilidad

Implementa `List` y `Deque`, lo que la hace versátil para usarse como lista, pila o cola.

## 3.2. Ventajas vs. Desventajas

### 3.2.1. Ventajas

- **Eficiencia en Modificaciones:** Inserciones y eliminaciones son rápidas y no requieren reordenamiento o redimensionamiento.
- **Uso Versátil:** Su diseño soporta operaciones de cola y pila además de funciones de lista.

### 3.2.2. Desventajas

- **Acceso Secuencial:** Localizar elementos por índice es más lento comparado con estructuras basadas en arreglos como `ArrayList`.
- **Consumo de Memoria:** El almacenamiento de referencias adicionales aumenta el uso de memoria.

## 3.3. Aplicaciones

Ideal para escenarios con manipulaciones frecuentes, donde las operaciones de inserción y eliminación superan en número a las consultas por índice.

## 3.4. Ejemplo de Uso

```java
LinkedList<String> nombres = new LinkedList<>();
nombres.add("Alice");
nombres.addFirst("Bob");
nombres.addLast("Charlie");

// Iteración
nombres.forEach(System.out::println);

// Modificación
nombres.removeFirst();
nombres.removeLast();
```

Este ejemplo demuestra cómo `LinkedList` facilita agregar, remover e iterar sobre elementos, destacando su eficiencia en operaciones de modificación.

## 3.5. Extra: Métodos

`LinkedList` en Java ofrece una rica colección de métodos que la hacen versátil para una amplia gama de usos. Aquí te presento algunos de los métodos más utilizados de `LinkedList`, que destacan su funcionalidad tanto como lista como cola doblemente terminada (`Deque`):

### Métodos de Manipulación de Listas

- **`add(E e)`**: Añade el elemento `e` al final de la lista.
- **`add(int index, E element)`**: Inserta el elemento `element` en la posición `index`, desplazando los elementos existentes.
- **`addFirst(E e)`**: Inserta el elemento `e` al principio de la lista.
- **`addLast(E e)`**: Añade el elemento `e` al final de la lista.
- **`remove(Object o)`**: Elimina la primera ocurrencia del objeto `o` de la lista.
- **`remove(int index)`**: Elimina el elemento en la posición `index`.
- **`removeFirst()`**: Elimina y retorna el primer elemento de la lista.
- **`removeLast()`**: Elimina y retorna el último elemento de la lista.
- **`get(int index)`**: Retorna el elemento en la posición `index`.
- **`getFirst()`**: Retorna el primer elemento de la lista.
- **`getLast()`**: Retorna el último elemento de la lista.
- **`set(int index, E element)`**: Reemplaza el elemento en `index` por `element`.
