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

# 3.3. Restricciones (constraints)

Las restricciones, como se comentó anteriormente, representan uno de los elementos de un modelo de datos. Para el caso del modelo relacional, se considera la siguiente clasificación.

| Nombre de la restricción y otros elementos | Implementación en un RDBMS |
| ------------------------------------------ | -------------------------- |
| Restricciones de llave primaria            | PRIMARY KEY                |
| Restricciones de referencia                | FOREIGN KEY                |
| Restricciones de integridad                | CHECK                      |
|                                            | NULL, NOT NULL             |
|                                            | UNIQUE                     |
| Validación por trigger.                    | TRIGGER                    |

## 3.3.1. Restricciones de llave primaria

Una llave primaria (PK) es una columna o conjunto de columnas cuyos(s) valor(es) identifican de manera única a un registro.

El RDBMS implementa esta restricción haciendo uso de las 2 siguientes restricciones de integridad:

- UNIQUE.
- NOT NULL.

Los siguientes puntos permiten identificar a una PK de una tabla:

- Dependencia funcional
- Consideraciones requeridas
- Consideraciones opcionales
- Tipos de llaves primarias

### 3.3.1.1. Dependencia funcional

Consiste en determinar y verficar el o los campos que actuarán como PK.

Definición: El atributo "B" es funcionalmente dependiente de un atributo "A" si cada valor de la columna "A" determina uno y solo un valor de la columna "B". Se expresa: A -> B

De lo anterior, se puede concluir que "A" puede tomar el rol de llave primaria, siempre y cuando A, también pueda determinar el valor de las demás columnas. Es decir: A -> B, C, D, E, ...

### 3.3.1.2. Consideraciones requeridas

La PK debe ser un campo cuyo valor nunca debe ser modificado después de que se ha asignado o almacenado en la BD. Modificar PKs implica modificar los valores de todas las referencias en tablas relacionadas lo que puede puede originar inconsistencias.

Como se mencionó anteriormente, los campos que actúen como PK no deben contener valores nulos, ni tener valores duplicados.

### 3.3.1.3. Consideraciones opcionales

Debido de que el RDBMS asigna un índice único a los campos que actúen como PK, se requiere procesamiento adicional para crear, almacenar y mantener este índice.

El mejor desempeño se obtiene cuando el índice es construido sobre un atributo cuyo tipo de dato es numérico entero, de preferencia, valores consecutivos no duplicados iniciando en 1.

Por lo anterior, si se desea obtener este beneficio, la PK de una tabla puede ser formada por un nuevo atributo que cumpla con estas características. A este tipo de llave primaria se le conoce como llave primaria artificial.

### 3.3.1.4. Tipos de llaves primarias

- **Llave primaria natural:** Son representadas por atributos nativos o propios de una entidad. Un atributo nativo es aquél que tiene significado para las reglas de negocio del caso de estudio.

- **Llave primaria artificial:** Es representada por un campo que se agrega a una tabla que no tiene significado alguno para las reglas de negocio, su única función es actuar como llave primaria que cumple con todos los requisitos anteriores:

  - Campo numérico, entero y consecutivo (mejora el desempeño del índice).
  - Valores únicos y no nulos.
  - Su valor nunca es modificado.

- **Llave primaria compuesta:** Una PK compuesta está formada por más de un atributo. El valor de la PK compuesta se forma por la **combinación** de los valores de los N campos que la integran. Para determinar si un registro está duplicado se deberá buscar la existencia de la combinación considerando valores y orden de los valores en la combinación, en la tabla.

## 3.3.2. Restricciones de referencia (Llave foránea, FK)

Para poder realizar la implementación de los tipos de relaciones existentes entre 2 entidades, el modelo relacional hace uso del concepto de Llave Foránea (Foreign Key, FK).

- Una FK es un campo dentro de una tabla B que hace referencia a la PK de una tabla A, o en su defecto a un atributo con restricción **UNIQUE**.
- Típicamente a la tabla que propaga la PK se le conoce como **tabla padre**, y a la tabla sobre la que se propaga la PK se le conoce como **tabla hija**.
- Este tipo de restricciones se emplea para relacionar entidades.

### 3.3.2.1. Variantes

- Si la PK de la tabla padre es compuesta, entonces ambos atributos pertenecientes a la PK compuesta se propagan a la tabla B.

- La FK propagada por la tabla padre puede formar parte de la PK de la tabla hija, representando así tanto una FK como una PK; es importante tener en cuenta que si se propaga como parte de la PK de la tabla hija, entonces la FK no podrá repetirse y solo será asociada a un registro de la tabla hija (relación 1:1).

### 3.3.2.2. Consideraciones

- El RDBMS verificará de manera automática que el valor asignado a una FK en la tabla hija exista como PK en la tabla padre. En caso de no ser así, se generará el error **_Referential Integrity Violation_**.

- Si se intenta eliminar un registro de la tabla padre que está relacionado con uno o más registros en la tabla hija, se producirá un error de violación de restricción con el mensaje **_Registros en la tabla hija encontrados_**.

- Si se agrega a la tabla hija un registro con la cuya FK no existe como PK en la tabla padre, se producirá un error de violación de integridad con el mensaje **_Registro en la tabla padre no encontrado_**.

## 3.3.3. Restricciones de integridad

Ayudan a mantener el estado correcto o verídico de los datos (consistencia e integridad). Son verificadas por el RDBMS de forma automática.

Tipos de restricciones de integridad:

- NOT NULL
- CHECK
- UNIQUE

### 3.3.3.1 NOT NULL

Al asignarlo a un atributo, garantiza que dicho atributo no tenga valores nulos (campo obligatorio). Un valor nulo significa la ausencia de valor (no hay dato); valor nulo NO significa lo siguiente:

- Cadena vacía ("")
- Un cero (0)
- Un espacio (" ")
- Una cadena null ("null")

Por lo tanto, cuando se tiene un valor nulo nos referimos a nada, una casilla vacía, sin dato.

Para representar la ausencia de valor al mostrar una tabla de datos, **algunos** RDBMS muestran la palabra **null** pero no es que dicha palabra esté almacenada, es solo su representación gráfica al ser mostrado a un usuario para no dejar la casilla en blanco.

Si se omite el valor en un atributo NOT NULL, se obtendría de nuevo un **_Error de violación de restricción_**

### 3.3.3.2 CHECK

CHECK verifica algo, y es implementada con una expresión booleana. Normalmente se implementa a un atributo de una tabla para verificar que se inserten valores correctos (valores dentro de un rango, etc.), de lo contrario se generaría un **_Error de violación de restricción_**

Ejemplo:

```SQL
check (sueldo_mensual >= 5000 and sueldo_mensual <= 999999)
```

Es importante mencionar que la expresión booleana tiene acceso a atributos del mismo registro que se está insertando, sin embargo, no tiene mayor alcance, es decir, no tiene acceso a datos de otros registros de la tabla o a registros de otras tablas.

### 3.3.3.3. UNIQUE

Como su nombre lo indica, es una restricción que al aplicarse a un atributo, evita que ese atributo tenga valores duplicados. A diferencia de la restricción PK, la restricción UNIQUE puede tener valores nulos (obvio, solo en caso de que no se aplique también la restricción NOT NULL al atributo)
