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

# 2.2.1. Entidad

Una entidad es cualquier cosa a partir de la cual se realiza la obtención de datos. Representa un objeto del mundo real, los cuales pueden ser de 2 tipos:

- Objetos físicos: silla, escuela, pizarrón, etc.

- Objetos abstractos: viaje, reservación, inscripción, curso, certificado, etc.

Generalmente se identifican a través de _sustantivos en singular_. Una estrategia sencilla para detectar las posibles entidades es subrayar todos los sustantivos de un caso de estudio.

# 2.2.2. Instancia de una entidad

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

# 2.2.3. Atributo

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
