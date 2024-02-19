# 3.1. Características del modelo relacional

- Define tres principales componentes:
  - **Estructura lógica:** Se refiere a cómo los datos son visualizados (forma tabular) y está representada por **relaciones**.
  - **Reglas de integridad:** Permiten cuidar la integridad de los datos.
  - **Operaciones:** Definen la manera en que se van a manipular los datos.

# 3.2. Estructura lógica de los datos.

La estructura lógica de los datos se basa en los siguientes conceptos:

- **Relación**: Toda una tabla de datos es una Relación. Corresponde al concepto de entidad en un modelo de datos.
- **Tupla:** Corresponde a cada fila de la tabla. En relación con un modelo de datos, corresponde a una instancia.
- **Atributo**: Corresponde a cada una de las columnas de una tabla. También se le llama campo.
- **Cardinalidad**: Corresponde al número de tuplas de una relación. En términos de modelo de datos, se refiere al número de instancias de una entidad.
- **Grado**: Corresponde al número de atributos de una relación.
- **Dominio**: Corresponde al rango de valores posibles de un atributo.

## 3.2.1. Tablas

Representa la unidad primaria de almacenamiento y la implementación del concepto de relación. Una tabla generalmente representa a una entidad identificada en el diseño conceptual.

- Cada tupla (registro) representa la ocurrencia de una relación (entidad)
- Cada columna representa a un atributo de la entidad, y esta debe tener nombre único
- Los datos de una columna deben ser del mismo tipo de dato.
- El orden de las columnas es irrelevante.
- Cada columna tiene un rango de valores (dominio).
- Una tabla puede contar con una o varias columnas que identifican a un registro de manera única llamada **llave primaria**.
- Una tabla puede contar con una o más columnas empleadas para relacionarse con otras tablas, llamadas **llaves foráneas**

# NOTA: ME QUEDE EN CLASE 8 MIN. 00:24:06
