# 2.1. Modelos de datos

Un modelo de datos se refiere a una representación, generalmente gráfica, que describe la estructura de los datos y sus características respecto a un caso de estudio. Representa una abstracción del problema a resolver.

Uno de los principales problemas en el diseño de bases de datos, es que usuarios/clientes, ingenieros, diseñadores, etc. visualizan los datos de manera distinta.

La construcción de un modelo de datos permite contar con una visión única y correcta de la estructura y comportamiento de los datos aplicada a un problema real. Ayuda a entender el contexto y el entorno de un problema.

Los modelos de datos representan una herramienta de comunicación entre los involucrados en el proyecto asociado con el diseño de una base de datos.

# 2.2. Elementos de un modelo de datos (independiente de su tipo)

Cualquier modelo de datos debe contar con los siguientes elementos básicos:

- Entidades
- Atributos
- Relaciones entre entidades
- Restricciones

## 2.2.1. Entidad

Una entidad es cualquier cosa a partir de la cual se realiza la obtención de datos. Representa un objeto del mundo real, los cuales pueden ser de 2 tipos:

- Objetos físicos: silla, escuela, pizarrón, etc.

- Objetos abstractos: viaje, reservación, inscripción, curso, certificado, etc.

Generalmente se identifican a través de _sustantivos en singular_. Una estrategia sencilla para detectar las posibles entidades es subrayar todos los sustantivos de un caso de estudio.

## 2.2.2. Instancia de una entidad

Mientras que una entidad se define a través de sus atributos, una instancia de dicha entidad, es representada por un objeto en particular en donde se conoce el valor de cada uno de sus atributos.

_Ejemplos:_

- **Entidad:**

  - Silla (descripción, tipoMaterial, color, estilo, peso)

- **Instancias:**

  - Silla 1 ("De comedor", "Madera", "Café", "Rústico", 5.6)
  - Silla 2 ("Reclinable", "Metal con piel", "Negra", 6.4)

- **Entidad:**

  - Viaje (nombre, origen, destino, fechaSalida)

- **Instancias:**
  - Viaje 1 ("Excursión de graduación", "México DF", "Acapulco", "01/01/2011")

## 2.2.3. Atributo

Un atributo es una característica de una entidad. Un atributo es similar a un "campo" (field) en un sistema de archivos. Normalmente las entidades se definen en términos de su lista de atributos:

_Ejemplos:_

- Silla (material, color, peso)
- Escuela (num_salones, dirección, tipo)
- Curso (nombre, nivel, fecha_inicio, fecha_fin, cupo_maximo)

Un error común que ocurre al momento de identificar los elementos de un modelo de datos, es la posibilidad de confundir a una entidad de un atributo o viceversa. Los siguientes puntos pueden considerarse para facilitar y realizar la identificación de forma correcta:

- **Cómo identificar correctamente a una entidad**

  - Duplicados

    - Revisar si existen sustantivos que representan sinónimos. Estos deberán descartarse. Por ejemplo, Empleado, Trabajador, etc.

  - Cardinalidad

    - En algunas ocasiones se detecta que existirá una sola instancia de la entidad propuesta. No tiene sentido contar con una entidad que solo contará con una instancia, por lo que puede ser descartada.

  - Roles

    - En algunas ocasiones se detecta la ocurrencia de roles asociados a una misma entidad. Por ejemplo, la entidad empleado cuenta con tres roles: Administrador, Investigador, Profesor. En el tema 5 se revisará este escenario. Por ahora es posible aplicar el siguiente caso:

      - Si los roles cuentan con atributos particulares, se conservan, de lo contrario, se eliminan.

      - En el tema 5 se revisa la forma en la que se realiza el modelado de estos roles particularmente cuando definen sus propios atributos.

  - Ambigüedades

    - Evitar la definición de entidades que no representen a un objeto (sustantivo) o que el sustantivo no define a un objeto de interés para el caso de estudio. Ejemplos de palabras ambigüas: **catálogo**, **revisar**, **histórico**, etc.

- **Cómo evitar confundir un atributo de una entidad**

  - Número de atributos

    - Si se identifican al menos 2 atributos asociados a un mismo objeto, entonces es factible proponer una nueva entidad.

    - Si solo se identifica un solo atributo, en algunas ocasiones puede ser factible proponer una nueva entidad a pesar de tener un solo atributo cuando ocurre alguna de las siguientes situaciones.

      - **El atributo aparece en varias entidades.** Esto significa que sus valores pudieran repetirse varias veces en distintos lugares. En este caso se crea una entidad y se le asigna un identificador. En lugar de repetir N veces los valores del atributo, se crea una relación entre la nueva entidad con las N entidades donde aparece el atributo y se propaga dicho identificador.

      - **El atributo aparece en una sola entidad.** Si los valores del atributo aparecen con alta frecuencia, es posible crear una nueva entidad y relacionarla a través de un identificador.

      - **Los valores del atributo cambian con alta frecuencia.** Al tener múltiples copias del mismo valor ya sea en la misma o en diferentes entidades, un cambio de valor implicar cambiar todas las copias. Esto implica complejidad y aumenta la posibilidad de inconsistencias. Por lo tanto, se justifica crear una entidad con un identificador y su atributo.

      - **Los valores del atributo son de longitud relativamente grande.** A mayor longitud o tamaño de los valores de un atributo requiere mayor almacenamiento y mayor procesamiento para almacenar un mismo valor de forma repetida, aumentando la posibilidad de inconsistencias si sus valores son susceptibles a cambios.

Ejemplo
Suponer las siguientes entidades que fueron detectadas para realizar la administración de una empresa que cuenta con una cadena de agencias de autos distribuidas en todo el mundo. Existen tres tipos de agencias A, B y C.

```text
Auto (num_serie, marca, modelo, pais_manufactura, precio)
Cliente (RFC, CURP, email, calle, colonia, municipio, estado)
Agencia (clave, calle, colonia, municipio, estado, pais, tipo)\
```

¿Qué atributos podrían ser considerados como entidades para evitar los problemas mencionados anteriormente?

Respuesta: marca, modelo, pais, calle, colonia, municipio y estado.

Los siguientes puntos permiten decidir si se consideran como entidades:

- Los valores de estos atributos pueden repetirse con gran frecuencia.
- Sus valores son cadenas relativamente grandes
- Los valores de estos atributos se modifican con muy baja frecuencia. Esto podría minimizar la posibilidad de inconsistencia.
- Si los requerimientos indican la necesidad de contar con un control estricto de la direcciń y es crítico minimizar inconsistencias, la separacioón y el uso de entidades (catálogos) puede ser opción. Como se mencionó anteriormente, esta decisión puede tener impacto en el desempeño.

## 2.2.4. Relaciones entre Entidades

Para comprender cómo se relacionan las entidades, es crucial determinar el tipo de relación que existe entre ellas. Este análisis se simplifica con la siguiente notación:

| Tipo de Relación | Notación     |
| ---------------- | ------------ |
| Uno a Uno        | 1:1          |
| Uno a Muchos     | 1:N o 1..\*  |
| Muchos a Uno     | N:1 o \*..1  |
| Muchos a Muchos  | N:M o \*..\* |

La identificación del tipo de relación entre dos entidades implica evaluar cuántas instancias de A se asocian con una instancia de B y cuántas instancias de B se asocian con una instancia de A.

## 2.2.5. Restricciones

Las restricciones son condiciones aplicadas a entidades o sus elementos para garantizar la integridad de los datos. Estas restricciones, derivadas del análisis del caso de estudio y las reglas de negocio, pueden ser automáticas o programadas. Ejemplos incluyen PL/SQL.

# 2.3. Reglas de Negocios

Las reglas de negocio son enunciados claros y concisos que describen políticas, hechos o procedimientos dentro de una organización. Su importancia radica en la consecución de objetivos organizativos, y están intrínsecamente relacionadas con los procesos de negocio.

Estas reglas deben expresarse en un lenguaje natural comprensible por todos los involucrados, siendo atómicas, es decir, lo más simples posible, sin divisibilidad en sub-enunciados.

En el diseño de bases de datos, las reglas de negocio desempeñan un papel crucial al permitir definir los elementos esenciales del modelo de datos, que incluyen entidades, atributos, relaciones y restricciones. Estas reglas no solo estructuran la visión de la organización sobre la gestión de datos, sino que también proporcionan un estándar compartido. Este estándar facilita la comprensión del negocio por parte de diseñadores y otros participantes en el proyecto. De esta manera, las reglas de negocio se erigen como pilares fundamentales para una implementación efectiva y comprensión unificada en el diseño de bases de datos.

```text
Ejercicio: Caso de estudio EU Rent.

Considere el siguiente caso de estudio asociado con un sistema de renta de automóviles. Realice una lectura cuidadosa del caso de estudio, determinar los elementos del modelo de datos:

A. Entidades
B. Reglas de negocio
C. Relaciones entre entidades

Modelo de negocio de EU-Rent:
EU-Rent es una compañía que se dedica a la renta de autos.

Sucursales
La compañía cuenta con más de 1000 sucursales en ciudades del país. Las sucursales están distribuidas en 3 diferentes regiones: región A, región B y región C. Una región está integrada por varias ciudades, y en una ciudad pueden existir varias sucursales.

Personal de las sucursales
Cada sucursal cuenta con un gerente y con varios agentes de ventas encargados de atender a los clientes. Adicionalmente, cada sucursal cuenta con hasta 3 ingenieros mecánicos para dar mantenimiento a los autos. Los gerentes solo pueden administrar a una sucursal, aunque los agentes, de así solicitarlo pueden trabajar en diferentes sucursales. Los empleados no pueden realizar rentas de autos.

Autos
Cada sucursal cuenta con un catálogo de autos para rentar. Un auto solo pertenece a una sucursal. Cada 3 meses o cada 10000 Km, el auto debe recibir servicio de mantenimiento. El auto puede tener varios servicios a lo largo de su vida útil. EU Rent ofrece 8 tipos de servicio de mantenimiento para ser aplicados a los autos que así lo requieran.

Clientes
Se requiere almacenar los siguientes datos del cliente: nombre, apellido paterno, apellido materno, email, RFC, dirección y teléfono.

Rentas
Un cliente puede rentar hasta 3 autos al mismo tiempo (máximo 3 por renta). Se registran los datos de la renta: fecha de solicitud, periodo de tiempo de la renta el cual puede ser hasta por un mes, el cliente que la solicita, y se asocian los autos que el cliente selecciona. Si el auto está en servicio, este no podrá ser rentado.

Facturas
Cada vez que el cliente realice una renta, se genera una factura, se requiere almacenar los siguientes datos: monto total, renta asociada y la fecha de elaboración.
```

Solución
A continuación se muestra la solución por pasos.

```text
1.- Generar la lista de entidades candidatas
- Región
- Ciudad
- Sucursal
- Gerente *
- Agente de ventas *
- Cliente
- Ingeniero mecánico *
- Agente
- Empleado **
- Auto
- Servicio de mantenimiento
- Mantenimiento
- Renta
- Factura
- Asesor *

2.- Descartar entidades con base en duplicados, cardinalidad, roles y ambiguedades.
Descartadas
- Mantenimiento: por duplicado y ambiguedad con Servicio de mantenimiento.
- Agente de ventas, gerente y agente: por redundancia y rol de la entidad Empleado sin atributos propios.
- Ingeniero mecánico: por rol de la entidad Empleado sin atributos propios.
- Asesor: no se menciona en el caso de estudio.
- Región: porque tiene más la estructura de un atributo; como entidad tendría pocas instancias y un solo atributo. Sus posibles valores son pocos (A, B y C) y de un solo caracter.
- Auto: porque no se mencionan atributos de interes ni relaciones.


Remanentes
- Sucursal: porque está relacionada con Región, Ciudad, Empleado.
- Cliente: porque el caso de estudio detalla atributos de interés del Cliente.
- Factura: porque el caso de estudio detalla atributos de interés de la Factura.
- Ciudad: porque tiene al menos dos atributos: nombre y región.
- Renta: porque el caso de estudio detalla atributos de interés de la Renta.
- Servicio de mantenimiento: Porque tiene al menos 2 atributos (tipo de servicio y empleado [hasta 3]), además, está relacionada con la entidad Empleado.

3.- Detectar reglas de negocio
- Un empleado puede ser gerente de una sucursal como máximo.
- Una renta incluye hasta tres autos.
- Un auto en servicio de mantenimiento no puede ser rentado.
- En una sucursal existen hasta tres ingenieros mecánicos.
- Un empleado no puede rentar autos.
- Un auto debe recibir servicio de mantenimiento cada tres meses
- Un empleado agente puede laborar en una o en más sucursales.
- Cada renta genera su correspondiente factura.
- En una ciudad pueden existir varias sucursales.
- Un auto es asignado a una sola sucursal

4.- Detectar relaciones entre entidades con base en las reglas de negocio.
Sucursal - Empleado (gerente): Una sucursal cuenta con un gerente y un gerente administra una sola sucursal. (1:1)
Ciudad - Sucursal: En una ciudad pueden existir varias sucursales y una sucursal pertenece a una sola ciudad (1:m)
Renta - Auto: Una renta puede incluir hasta tres autos y un auto puede ser rentado varias veces de manera no simultánea. (m:n)
Factura - Renta: Una factura se genera por cada renta y una renta genera una sola factura: (1:1)
Factura - Cliente:
Sucursal - Auto: Una sucursal puede tener varios autos y un auto pertenece a una sucursal. (1:m)
Servicio de mantenimiento - Auto: Un auto puede recibir varios servicios de mantenimiento en el tiempo y un servicio de mantenimiento se realiza a un solo auto (1:m)
Empleado (ing) - Servicio de mantenimiento: Un ingeniero mecánico puede realizar varios servicios de mantenimiento a lo largo del tiempo y un servicio de mantenimiento puede ser realizado por un solo ingeniero mecánico.
Sucursal - Empleado (agente): En una sucursal laboran varios agentes de ventas y un agente de ventas puede laborar en varias sucursales. (m:n)
Cliente - Renta: Un cliente puede rentar varias veces y una renta es solicitada por un solo cliente. (1:m)
```

# 2.4. Evoluación de los modelos de datos

- 50s < t < 70s: Sistemas de archivos
- 50s < t < 80s: Modelo jerárquico
- 60s < t < 90s: Modelo de red
- 70s < t: Modelo Relacional (RDBMS)
- 80s < t: Modelo Orientado a Objetos (OODBMS)
- 90s < t: Modelo Orientado a Objetos / Relacional (ORDBMS)
  - ORMs (Object Relational Mapping)
  - Soporte para procesamiento de documentos XML
  - Soporte para procesamiento de documentos JSON
  - Bases de datos multidimensionales
- 2000s < t: Modelos NoSQL
