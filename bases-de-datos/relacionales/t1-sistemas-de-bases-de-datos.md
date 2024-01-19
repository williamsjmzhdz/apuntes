# 1.1. Datos e Información

Los datos representan la herramienta principal para lograr los objetivos y el correcto funcionamiento de cualquier empresa.

```
Ejemplo

Imagina a un negocio tratar de realizar sus operaciones sin conocer ¿quiénes son sus clientes?, ¿qué productos vende?, ¿quiénes son sus deudores?. Toda esa información debe estar disponible para que el negocio funcione correctamente.
```

## 1.1.1 Dato

Un dato es la unidad mínima de información. Está representado por un símbolo (número, letra, signo, etc.) que se emplea para representar algún hecho, condición, valor, situación, cantidad, medida, etc.

Los datos por sí mismos no tienen ningún significado, son solo letras, caracteres, números, etc.

## 1.1.2 Información

Si a un conjunto de datos los procesamos, entonces podremos encontrar un significado, dando origen a la información.

La información por lo tanto, es el resultado de aplicar un procesamiento de datos a un conjunto de datos organizados y representados de forma correcta que revela o muestra un **significado**.

Dicho procesamiento puede ser tan simple o tan complejo como se requiera y normalmente se realiza a través de equipos de cómputo de forma automatizada y a grandes velocidades.

```
Ejemplo

A un conjunto de números que representan calificaciones los sumamos y los dividimos entre el número total de calificaciones: obtenemos un promedio, una pieza de información.
```

### 1.1.2.1. Características de la información

Al procesar los datos, la información obtenida debe contar con las siguientes características:

- Significado: Saber qué nos indica el conjunto de datos procesados.
- Importancia: Es importante para una correcta toma de decisiones.
- Vigencia: La información es válida por cierto periodo de tiempo.
- Validez: No sirve información que no es correcta: los datos deben estar bien representado y bien diseñados, aquí entran las bases de datos.
- Valor: Es el activo intangible volátil

### 1.1.2.2. Utilidad de la información

- Descubrir el significado: ¿Qué nos quieren decir estos datos?
- **Toma de decisiones:** De vital importancia inclusive para la supervivencia humana.

La generación de la información se realiza normalmente en 3 principales etapas:

1. Entrada o captura de datos
2. Representación y almacenamiento estructurado de datos en bruto (raw data)
3. Representación e interpretación del resultado del procesamiento de los datos (información).

# 1.2. Administración de los datos

Para poder obtener información útil y correcta de una fuente masiva de datos, surgen algunos requerimientos para la fuente de datos:

- Buen diseño de la base de datos

- Concurrencia

- Persistencia

- Acceso

- Integridad

- Respaldos

- Seguridad

- Lenguajes de acceso a datos

- Interfaces de comunicación: Local, remota, etc.

Para poder garantizar los requerimientos anteriores, es necesaria realizar una administración de los datos.

La herramienta que nos ayuda a implementar todos los requerimientos anteriormente listados es el llamado Sistema Administrador de Bases de Datos (Database Management System, DBMS).

# 1.3. Base de datos y Sistema Administrador de Bases de Datos (DBMS)

## 1.3.1. Base de datos

Una base de datos es una colección de datos interrelacionados que representan activos para obtener información de interés para un sistema de información y/o usuario final.

Los datos que constituyen a la base de datos, se almacenan de manera sistemática para su posterior uso.

La estructura de la base de datos (tablas y sus relaciones) es almacenada en archivos, típicamente llamados **Data files** que son independientes y desconocidos por el usuario. La única manera de acceder a los datos contenidos en ellos es usando un DBMS.

Los datos almacenados se dividen en dos grupos:

- Datos de interés para el usuario.
- Metadatos.

### 1.3.1.1. Datos de interés para el usuario (_datos del usuario_)

Representan la fuente para la generación de información de interés para el usuario final.

### 1.3.1.2. Metadatos (_Datos acerca de los datos_)

Se puede definir a los metadatos como características y restricciones de los datos de interés para el usuario. Algunos ejemplos de metadatos son:

- Tipo de dato
- Longitud
- Relaciones entre los datos
- Rango de valores

Los metadatos representan el llamado **diccionario de datos**.

## 1.3.2. Sistema Administrador de Bases de Datos (DBMS)

Es una colección de programas (software) encargado de administar la estructura de la base de datos y del control de acceso a los datos almacenados.

Sus funciones principales son:

- Actuar como intermediario entre el usuario y la base de datos.
- Implementar los requerimientos antes listados (ver punto 1.2).
- Aministrar el diccionario de datos.

```
Nota mental

Los datos se guardan en archivos llamados data files, los cuales son archivos binarios con extensión .dbf a los que el usuario final no puede acceder ni comprender. Solo el DBMS puede entender estos archivos, y esto se conoce como la estructura física de los datos.

La manera en que los datos se almacenan en los data files es independiente y desconocida para el usuario. La representación de los datos en forma de tabla que utiliza el DBMS es simplemente para facilitar la comprensión del usuario. Sin embargo, esto no significa que los datos se almacenen de esa manera en los data files ni que cada data file corresponda a una tabla en el modelo relacional. A las tablas y sus relaciones se les conoce como la vista lógica de la base de datos.
```

# 1.4. Integridad, Redundancia y Consistencia

## 1.4.1. Redundancia

La redundancia se presenta cuando un mismo dato se almacena innecesariamente en diferentes ubicaciones, lo que puede ocasionar inconsistencia de datos y pérdida de rendimiento. Es importante distinguir entre redundancia necesaria y redundancia innecesaria.

## 1.4.2. Inconsistencia de Datos

La inconsistencia de datos ocurre cuando hay dos o más versiones de un mismo dato con valores diferentes, generando conflictos entre las versiones.

## 1.4.3. Integridad de Datos

La integridad de datos es una condición en la cual todos los datos de una base se consideran consistentes con respecto al mundo real y su contexto. En una base de datos con integridad, los datos son adecuados (sin inconsistencias) y varídicos (conducen a resultados consistentes).

## 1.4.4. La Redundancia no Siempre es Negativa

En ocasiones, se permite cierto nivel de redundancia siempre y cuando se implemente un control adecuado para prevenir inconsistencias. La existencia de cierta redundancia puede ser justificada por razones de rendimiento. Si se normaliza excesivamente las tablas para eliminar la redundancia, puede impactar negativamente el rendimiento de la base de datos al requerir operaciones de join costosas cada vez que se consulten datos. En estos casos, se busca un equilibrio entre normalización y rendimiento.

# 1.6 Sistema de bases de datos

Un sistema de bases de datos está integrado por los siguientes elementos.

- Hardware (servidores, servidores de almacenamiento, componentes de red).
- Software
  - Sistemas operativos (MacOS, Windows, Fedora, Ubuntu, Mint, Oracle Linux, etc.)
  - DBMS (PostgreSQL, MySQL, MariaDB, Oracle, etc.).
  - Programas de utilería, administración, monitoreo, etc.
- Personal
  - Administradores del S.O.
  - Usuario final
  - Rol asociado con la base de datos (ver siguiente tabla).

# 1.7 Metodología de diseño de bases de datos

Para realizar el correcto diseño de una base de datos se requiere del uso de una metodología que permite identificar las diferentes etapas, así como las diferentes herramientas a utilizar. Una de las principales metodologías se ilustra en el siguiente diagrma.

- **Especificación de requerimientos**

  - Análisis
  - Reglas de negocio
  - Entrevistas con el usuario

- **Diseño conceptual**

  - Independiente a tecnologías, hw, sw y al modelo de datos (relacional, no relacional, POO, etc.)
  - Formato Chen
  - Elementos de un modelo de datos
  - Artefacto producido:
    - **Modelo Entidad Relación (MER)**

- **Diseño lógico**

  - Dependiente del modelo de datos
  - Independiente al DBMS
  - Formato Crow's foot
  - Formato IDEF1X
  - Normalización
  - Conceptos del Modelo Relacional
  - Artefacto producido:
    - **Modelo Relacional (MR)**

- **Diseño físico**
  - Dependiente del DBMS
  - Requerimientos no funcionales
  - Artefacto producido:
    - **Esquema físico**
