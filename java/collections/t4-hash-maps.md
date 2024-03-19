# 4. HashMap

`HashMap` en Java es una implementación de la interfaz `Map` que utiliza una tabla hash. Es una estructura de datos que almacena pares clave-valor, donde cada clave es única.

## 4.1. Características Principales

### 4.1.1. Almacenamiento Basado en Hash

Utiliza una función hash para determinar dónde almacenar cada par clave-valor en la estructura interna, lo que permite búsquedas eficientes.

### 4.1.2. Claves Únicas

Cada clave en un `HashMap` debe ser única. Si se intenta insertar un par clave-valor con una clave que ya existe, el valor anterior se reemplazará por el nuevo.

### 4.1.3. Valores Nulos

Permite almacenar una clave nula (`null`) y múltiples valores nulos.

## 4.2. Ventajas vs. Desventajas

### 4.2.1. Ventajas

- **Acceso Rápido:** El acceso a los elementos es muy rápido (en promedio O(1)) debido al uso de la función hash.
- **Flexibilidad:** Puede almacenar claves y valores de cualquier tipo de objeto.

### 4.2.2. Desventajas

- **Orden No Garantizado:** Los elementos no se almacenan en ningún orden específico. Para mantener el orden de inserción, considera usar `LinkedHashMap`.
- **Concurrencia:** No es sincronizado. Si se requiere concurrencia, se debe considerar `ConcurrentHashMap` o sincronizar manualmente.

## 4.3. Operaciones Comunes

### 4.3.1. Inserción y Acceso

- **`put(K key, V value)`**: Añade un par clave-valor al mapa o actualiza el valor de una clave existente.
- **`get(Object key)`**: Devuelve el valor asociado con la clave o `null` si la clave no existe.

### 4.3.2. Eliminación

- **`remove(Object key)`**: Elimina el par clave-valor asociado con la clave.

### 4.3.3. Iteración

- **`keySet()`**: Devuelve un `Set` de todas las claves.
- **`values()`**: Devuelve una colección de todos los valores.
- **`entrySet()`**: Devuelve un `Set` de los pares clave-valor, permitiendo iterar sobre ambos simultáneamente.

## 4.4. Ejemplo de Uso

```java
import java.util.HashMap;

public class EjemploHashMap {
    public static void main(String[] args) {
        HashMap<Integer, String> map = new HashMap<>();
        map.put(1, "Java");
        map.put(2, "Python");
        map.put(3, "C++");

        // Acceder a un elemento
        System.out.println(map.get(1)); // Imprime "Java"

        // Iterar sobre el mapa
        for (Integer key : map.keySet()) {
            System.out.println(key + ": " + map.get(key));
        }

        // Eliminar un elemento
        map.remove(2); // Elimina la clave 2 ("Python")
    }
}
```

Este ejemplo demuestra cómo insertar, acceder, iterar y eliminar elementos en un `HashMap`.
