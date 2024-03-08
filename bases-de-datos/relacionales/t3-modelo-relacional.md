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

### 3.3.3.4. Verificación empleando Triggers

- Un trigger es un programa PL/SQL que se ejecuta cuando ocurre algún evento, por ejemplo, antes o después de: insertar, modificar, eliminar, etc.

# 3.5 índices

Un índice es una estructura de datos, por lo tanto, requiere almacenamiento. El objetivo de un índice es incrementar el desempeño de una base de datos al realizar extracción o explotación de los datos en el menor tiempo posible; esto se logra al minimizar el número de lecturas que el RDBMS tendría que realizar a cada uno de los archivos de datos asociados a una table.

Un índice se emplea principalmente para:

- Localizar datos sin tener que recorrer todo el contenido de una tabla.
- Realizar el ordenamiento de datos de uno o más campos.
- Garantizar la no duplicidad de los valores de un campo empleados, en especial en la PK.

## 3.5.1. Elementos de un índice

Un índice está conformado por dos elementos:

- Una llave: valor del atributo indexado (por ejemplo, una PK)
- Un valor: dirección en disco donde se encuentra el registro solicitado. En Oracle se conoce como **rowid**.

### 3.5.2. Rowids en Oracle

Oracle utiliza una cadena de 8 caracteres para representar las direcciones físicas de cada registro. El DBMS agrega una columna a cada tabla llamda **ROW_ID** en la que se almacena esta cadena.

Un rowid está compuesto por cuatro elementos:

- **OOOOOO**: Data Object Number ID que identifica el _segmento_ (grupo de datafiles) de la base de datos donde se encuentra el regitro.
- **FFF**: Número de datafile que contiene el registro.
- **BBBBBB**: Los números de bloques son relativos al datafile al que pertenecen, no al tablespace
- **RRR**: El número de registro en el bloque.

Un rowid representa la **estrategia más eficiente** para localizar un registro en la base de datos.

### 3.5.3. Cuándo emplear índices

Los siguientes puntos representan recomendaciones generales para decidir si a un atributo se le agrega o no un índice:

- Se realizan consultas frecuentes utilizando dicho atributo en el predicado (como condición).
- El dominio del atributo es amplio; no tiene sentido indexar un atributo con solo dos posibles valores, pues habría muchos rowids en una sola llave.
- El número de registros esperados como respuesta es pequeño (entre 2% y 4% del número de registros total de la tabla). En términos prácticos es lo mismo que el punto anterior, pero visto en términos de número de registros en vez de número de rowids.
- El número de registros de la tabla es grande; haciendo una analogía con un libro, no sirve de nada un índice para un libro con tres páginas. El número de registros es relativo, pero un número aproximado son 5000 registros para que el índice se use.

#### 3.5.3.1. Consideraciones

Hay que tener en cuenta que a mayor número de índices, el tiempo requerido para hacer una inserción, eliminación o una modificación de registros puede llegar a aumentar; esto debido a que el índice debe reestructurarse tras cada operación (similar al índice de un libro si se agrega, modifica o elimina una página/tema), por lo que al tener muchos índices, habría que hacer mucho trabajo de reestructuración, además de que ocuparíamos más memoria para almacenar muchos índices.

### 3.5.4. Tipos de índices

Cada tipo de índices define una estrategia y una serie de algoritmos para escaneos de la forma más eficiente posible. Independientemente de su tipo el objetivo es el mismo: escanear para recuperar rowids.

- HASH Index
- B+ Tree Index (Balanced Trees)
- Bitmap Index

#### 3.5.4.1. Hash Index

Es un índice basado en la estructura de datos Hashtable o Hashmap, donde para cada llave se calcula su código hash haciendo uso de la función hash sus componentes son los siguientes:

- Función hash: función que recibe como entrada el valor del atributo indexado (llave) y produce como salida el hash code.
- Hash code: índice del arreglo del hashmap donde se encuentra el rowid.

En una misma localidad del arreglo del hashmap puede haber varios rowids, cuando esto ocurre, se hace uso de una lista de rowids y se retorna la lista completa en caso de búsqueda de rowids.

A nivel general, los índices basados en tablas hash son muy eficientes realizando búsquedas, sin embargo, cuentan con las siguientes deventajas, lo que hace que este tipo de índice no sea muy utilizado en la práctica.

- No soporta ordenamiento de datos.
- No soporta consultas con operadores lógicos como **>, <, >=, <=**. Las búsquedas en una tabla hash siempre hacen uso del operador de igualdad **=**.
- Para tablas grandes se requiere mayor cantidad de memoria para construir la tabla hash.
- No soporta valores nulos. Columnas indexadas con valores nulos no son incluidas en este tipo de índice. Esto implica que si se intenta ejecutar la siguiente sentencia que justamente realice la búsqueda de valores nulos, el manejador no hará uso del índice debido a que la tabla hash no puede contener llaves nulas. El manejador tendrá que **recorrer toda la tabla** y encontrar los valores nulos.

```sql
select * from cliente where email is null
```

#### 3.5.4.2. Bitmap Index

Los índices tipo bitmap son una técnica de indexación utilizada en entornos donde las columnas de datos tienen un número limitado de valores únicos (dominio pequeño), como en atributos booleanos, categorias fijas o rangos de valores pequeños. Esta técnica es particularmente eficaz en bases de datos de almacenes de datos (data warehouses) y en sistemas donde las operaciones de lectura son más mucho más frecuentes que las operaciones de escritura.

##### 3.5.4.2.1 Funcionamiento

Un índice bitmap funciona creando una matriz (arreglo de 2 dimensiones), donde cada columna representa un posible valor del atributo indexado, y cada fila representa un registro de la tabla en la base de datos.

Un bit encendido (un 1) en una posición específica del bitmap, representa que el registro correspondiente a la fila del bitmap donde está el bit encendido, tiene el valor correspondiente a la columna del bitmap donde está el bit encencido, y un bit apagado (0) indica lo contrario.

Por lo anterior, los índices bitmap no almacenan directamente los **rowids** como parte del bitmap. Lo que proporcionan es una manera eficiente de determinar qué registros de la tabla satisfacen ciertos criterios de búsqueda basados en el atributo indexado. Por lo tanto, la obtención de los **rowids** es un mecanismo adicional que se basa en mapear los resultados del bitmap (los registros que cumplen con las condiciones de búsqueda) a los **rowids** específicos; esto lo hace el RDBMS de forma implícita. Algunos RDBMS pueden mantener una estructura de mapeo directo que asocia cada posición de bit en un bitmap con un **rowid** específico. Esta estructura puede ser una tabla o arreglo adicional donde el índice en el arreglo corresponde a la posición del bit en el bitmap (bitmap = arreglo dentro del arreglo o segundo nivel de la matriz) y el valor almacenado en ese índice es el **rowid** real. Cuando se accede a un bit específico del bitmap, se utiliza su posición para buscar en esta estructura de mapeo y obtener el **rowid** correspondiente.

##### 3.5.4.2.2. Ventajas

- Soporta valores nulos
- No requiere mucho almacenamiento y memoria para construirlo, ya que está compuesto de bits.
- Soporta atributos con dominio bajo (no importa si se repiten mucho los valores en los registros de la tabla).

##### 3.5.4.2.2. Desventajas

- No soporta ordenamiento de rowids (podrían estar ordenados los valores, pero no los rowids, que son los que interesa ordenar).
