## 2.1. Definición

Un arreglo es una estructura de datos que organiza elementos del mismo tipo en posiciones contiguas de memoria, identificados por un índice numérico. Proporciona un acceso eficiente a los elementos mediante índices.

## 2.2. Características principales

1. **Tipo de datos homogéneo:** Todos los elementos en un arreglo deben ser del mismo tipo.
2. **índices numéricos:** Cada elemento se identifica por un índice numérico, generalmente empezando desde 0.
3. **Tamaño fijo:** La longitud del arreglo se establece en el momento de la creación y no cambia durante la ejecución.

## 2.3. Ventajas

- **Acceso rápido:** Permite acceder a cualquier elemento de forma rápida mediante su índice.
- **Búsqueda y ordenamiento eficiente:** Facilita operaciones como búsqueda y ordanamiento.
- **Uso sencillo de memoria:** Almacena datos del mismo tipo de manera contigua.

## 2.4. Desventajas

- **Tamaño fijo:** Puede llevar a un desperdicio de memoria si no se utiliza completamente.
- **Inflexibilidad en la modificación dinámica:** La dificultad radica en ajustar dinámicamente un arreglo, especialmente para insertar o eliminar elementos en posiciones intermedias, ya que implica la necesidad de desplazar elementos. Cuando se alcanza el límite de elementos en un arreglo, no es posible redimensionarlo directamente; en su lugar, se requiere crear un nuevo arreglo con un tamaño mayor y copiar todos los elementos del arreglo original.

## 2.5. Operaciones recomendadas

- **Acceso:** Útil cuando se necesita acceder a elementos por posición de manera rápida.
- **Búsqueda y ordenamiento:** Eficiente para algoritmos que requieren recorrer cada dato de la estructura de datos y manipularlo/procesarlo.
- **Operaciones matriciales:** Excelente para representar matrices bidimensionales.

## 2.6. Operaciones no recomendadas

- **Inserción o eliminación:** Puede ser ineficiente debido a la necesidad de desplazar elementos.
- **Tamaño dinámico desconocido:** Si la cantidad de elementos puede cambiar dinámicamente, otras estructuras como listas enlazadas pueden ser más adecuadas.

En resumen, los arreglos son ideales cuando se necesita acceso rápido a elementos y el tamaño es conocido y fijo. Sin embargo, su inflexibilidad en la gestión dinámica puede hacerlos inadecuados para situaciones donde se requieren cambios frecuentes en el tamaño de la colección de datos.
