# 1. Estructura de Datos

Una estructura de datos es una forma organizada y especializada de almacenar y organizar datos en una computadora para que puedan ser utilizados y manipulados de manera eficiente. El objetivo de las estructuras de datos es facilitar el acceso, la búsqueda, la modificación y otras operaciones relacionadas con la gestión de datos.

Existen varias estructuras de datos, cada una diseñada para cumplir con ciertos requisitos y tareas específicas.

La elección de la estructura de datos adecuada depende de la naturaleza de los datos y de las operaciones que se realizarán con ellos. Cada estructura tiene sus ventajas y desventajas en términos de eficiencia y complejidad, y la elección correcta puede tener un impacto significativo en el rendimiento del programa.

# 2. CPU, RAM y almacenamiento en disco

Para entender la importancia de las estructuras de datos, tenemos que comprender como funciona un sistema informático a bajo nivel; en especial tres de sus componentes: CPU, RAM y almacenamiento en disco.

## 2.1. Unidad Central de Procesamiento (CPU)

La CPU es el componente principal de una computadora, se encarga de realizar la mayor parte del procesamiento de datos.

### 2.1.1. Funciones principales

- **Ejecución de instrucciones:** La CPU interpreta y ejecuta las instrucciones de los programas almacenados en la memoria. Estas instrucciones pueden ser operaciones aritméticas, lógicas, de transferencia de datos, etc.

- **Control de flujo:** La CPU coordina y controla el flujo de datos entre los diferentes componentes de la computadora, como la memoria, la entrada/salida y otros dispositivos periféricos.

- **Gestión de memoria:** La CPU administra el acceso a la memoria RAM, donde se almacenan temporalmente los datos y las instrucciones que necesita para ejecutar programas.

- **Interfaz con Dispositivos Entrada/Salida:** La CPU se encarga de gestionar la comunicación entre los dispositivos periféricos y el sistema operativo.

- **Operaciones aritméticas y lógicas:** La CPU realiza operaciones aritméticas y lógicas para procesar y manipular datos.

### 2.1.2. Características principales

- **Volicidad de reloj:** Medida en hercios (Hz), indica la cantidad de ciclos de reloj que la CPU puede realizar por segundo.

- **Núcleos:** Las CPU modernas a menudo tienen múltiples núcleos, lo que permite realizar tareas de manera simultánea. Cada núcleo puede procesar instrucciones de forma independiente.

- **Caché:** La memoria caché es una memoria de acceso rápido que almacena datos e instrucciones utilizados con frecuencia para acelerar el acceso a ellos.

- **Arquitectura:** Se refiere al diseño interno de la CPU, como la arquitectura x86 o ARM. Esto influye en la compatibilidad y el rendimiento con diferentes tipos de software.

- **Tecnología de fabricación:** Indica el tamaño de los transistores utilizados en la construcción de la CPU. Un menor tamaño suele permitir una mayor eficiencia energética y un rendimiento mejorado.

- **Unidad de Punto Flotante (FPU):** Realiza operaciones matemáticas más complejas, especialmente aquellas que involucran números decimales y de punto flotante.

## 2.2. Memoria de Acceso Aleatorio (RAM)

La memoria RAM (Random Access Memory) es un tipo de memoria volátil que se utiliza en sistemas informáticos para almacenar temporalmente datos y programas que están en uso o en ejecución.

### 2.2.1. Funciones principales

- **Almacenamiento temporal:** La RAM almacena temporalmente datos y programas que están siendo utilizados por la CPU en un momento dado. Cuando apagas la computadora, los datos almacenados en la RAM se pierden, ya que es una memoria volátil.

- **Rapido acceso y lectura/escritura:** La RAM proporciona un acceso rápido a los datos, permitiendo que la CPU lea y escriba información de manera eficiente. La velocidad de la RAM es crucial para el rendimiento general del sistema.

- **Ejecución de programas:** Los programas en ejecución se cargan en la RAM para que la CPU pueda acceder rápidamente a las instrucciones y datos necesarios. Cuanta más RAM tenga un sistema, más programas y datos puede manejar simultáneamente sin tener que recurrir constantemente a la memoria de almacenamiento más lenta, como un disco duro.

- **Almacenamiento de variables y datos de usuario:** La RAM también almacena variables y datos temporales generados durante la ejecución de programas. Esto incluye datos de usuario, resultados intermetidos, pilas de llamadas y otros elementos necesarios para el funcionamiento de los programas.

### 2.2.2. Características principales

- **Volatilidad:** La RAM es volátil, lo que significa que los datos almacenados en ella se pierden cuando se apaga la computadora. A diferencia del almacenamiento no volátil, como los discos duros o las SSD, que retienen la información incluso cuando el sistema está apagado.

- **Velocidad:** La RAM es considerablemente más rápida que los dispositivos de almacenamiento a largo plazo (discos duros, SSD). La velocidad de la RAM se mide en megahercios (MHz) o gigahercios (GHz), y una mayor velocidad contribuye a un rendimiento más rápido.

- **Capacidad:** La capacidad de la memoria RAM se mide en gigabytes (GB) o terabytes (TB). Los sistemas modernos suelen tener entre 4 GB y 64 GB de RAM, o incluso más en sistemas de alto rendimiento.

- **Tipos de RAM:** Hay varios tipos de RAM, incluyendo DDR (Double Data Rate), DDR2, DDR3, y DDR4, que representan diferentes generaciones con mejoras en velocidad y eficiencia.

- **Latencia:** La latencia de la RAM, medida en ciclos de reloj, representa el tiempo que tarda la memoria en responder a una solicitud de la CPU. Una menor latencia es deseable para un rendimiento más rápido.

# 2.3. Almacenamiento en disco (Discos duros, SSD)

El almacenamiento no volátil se refiere a dispositivos de almacenamiento de datos que retienen su información incluso cuando la corriente eléctrica se apaga.
Algunos ejemplos comunes de almacenamiento no volátil son los discos duros (HDD) y las unidades de estado sólido (SSD).

## 2.3.1. Funcionalidades principales

- **Retención de datos:** La característica más destacada del almacenamiento en disco es su capacidad para retener datos a largo plazo incluso cuando el dispositivo está apagado. Esto contrasta con la memoria RAM, que pierde su contenido cuando se corta la alimentación.

- **Almacenamiento a largo plazo:** Estos dispositivos son ideales para almacenar grandes cantidades de datos de manera persistente, como sistemas operativos, programas de software, archivos multimedia y documentos.

- **Arranque del S.O:** El sistema operativo y otros programas esenciales se cargan desde el almacenamiento no volátil durante el proceso de arranque de la computadora. Esto permite que la máquina inicie desde un estado apagado y ejecute programas sin necesidad de volver a cargarlos/instalarlos cada vez.

- **Almacenamiento de datos de usuario:** Además de contener el S.O, el almacenamiento en disco se utiliza para almacenar datos de usuario, como documentos, fotos, videos y otros archivos. Estos datos permanecen intactos incluso después de apagar la computadora.

## 2.3.2. Características principales

- **Tipo de tecnología:**

  - **HDD:** Utiliza discos magnéticos giratorios para almacenar datos. Los datos se leen y escriben mediante cabezales magnéticos que se mueven sobre los discos.
  - **SSD:** Utiliza memoria flash para almacenar datos. No tiene partes móviles y ofrece velocidades de lectura y escritura más rápidas que los discos duros.

- **Velocidad de acceso:**

  - **HDD:** Tiende a tener tiempos de acceso más lentos en comparación con los SSD debido a la naturaleza mecánica de los discos giratorios.
  - **SSD:** Ofrece tiempos de acceso más rápidos y velocidades de transferencia de datos más altas, ya que no hay partes móviles y la lectura/escritura se realiza electrónicamente.

- **Durabilidad:**

  - **HDD:** Puede ser más susceptible a daños por golpes o caídas debido a sus partes móviles.
  - **SSD:** Al no tener partes móviles, es generalmente más resistente a golpes y vibraciones.

- **Capacidad:**

  - **HDD:** Tradicionalmente, los discos duros han ofrecido mayores capacidades de almacenamiento en comparación con los SSD, especialmente en términos de almacenamiento masivo.
  - **SSD:** Las capacidades de almacenamiento de los SSD han aumentado con el tiempo y ahora están disponibles en tamaños significativos.

- **Consumo de energía:**

  - **HDD:** Tiende a consumir más energía en comparación con los SSD.
  - **SSD:** Generalmente consume menos energía, lo que puede traducirse en una mejor eficiencia energética.

- **Vida útil:**
  - **HDD:** Puede tener una vida útil más larga en términos de ciclos de escritura y reescritura.
  - **SSD:** Aunque la tecnología ha mejorado, los SSD pueden tener limitaciones en el número de ciclos de escritura, pero su vida útil es suficiente para un uso típico.

# 3. Operaciones en estructuras de datos

Como sabemos, las estructuras de datos son colecciones de datos organizadas y estructuras para hacer más eficiente la manipulación de datos de acuerdo a la naturaleza de un problema a resolver.

La manipulación de datos se refiere a ejecutar operaciones sobre los datos almacenados en una estructura de datos. Las operaciones más comunes son:

- **Acceso:** Acceder a un dato específico de una colección de datos.
- **Inserción:** Agregar un nuevo dato a una estructura de datos.
- **Eliminación:** Eliminar un dato de la estructura de datos.
- **Recorrer:** Acceder a cada dato de la estructura de datos exactamente una vez con el objetivo de procesarlo.
- **Búsqueda:** Encontrar la locación de un dato en la estructura de datos.
- **Ordenamiento:** Ordenar de acuerdo a un criterio, los datos dentro de la estructura de datos.
