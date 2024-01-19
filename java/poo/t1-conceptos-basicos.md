## 1.1. Programación Orientada a Objetos (POO)

La Programación Orientada a Objetos (POO) es un paradigma de programación que se centra en modelar entidades del mundo real, representándolas como objetos de software. Estos objetos poseen propiedades, denominadas atributos, y comportamientos, conocidos como métodos. El propósito principal de la POO es proporcionar una estructura organizada para el código, facilitando así la comprensión y mantenimiento del sistema.

## 1.2. Clase

En programación orientada a objetos, una clase se define como un tipo de dato personalizado, constituido por un bloque de código especial que incluye atributos y métodos. Podemos considerar una clase como una plantilla para la creación de objetos.

Una clase puede acceder a atributos y métodos estáticos, pero no a atributos y métodos de instancia.

## 1.3. Objeto

Un objeto, por otro lado, representa una instancia específica de una clase. Contiene valores concretos para los atributos definidos por la clase y puede interactuar con otros objetos, ya sean de la misma clase o de clases diferentes.

En términos sencillos, podemos crear múltiples objetos a partir de una misma clase, y cada objeto puede tener valores distintos para los atributos definidos por esa clase.

Un objeto puede acceder tanto a atributos y métodos estáticos como de instancia.

## 1.4. Atributo o Campo (Field)

Un atributo o campo se refiere a una variable dentro de una clase que describe una propiedad específica de dicha clase. Por ejemplo, una clase de **`Auto`** podría tener un atributo llamado **`color`**.

Existen dos tipos de atributos o campos: los estáticos y los de instancia.

### 1.4.1. Atributos Estáticos

Los atributos estáticos pertenecen a la clase en sí misma, no a las instancias u objetos creados a partir de ella. Pueden ser accedidos tanto por la clase como por sus instancias, manteniendo siempre el mismo valor para la clase y sus instancias, ya que se almacenan en una ubicación de memoria especial y única.

### 1.4.2. Atributos de Instancia

Los atributos de instancia son propios de cada objeto creado a partir de la clase y no de la clase en sí misma. El valor de un atributo de instancia no se reserva en memoria ni tiene un valor asignado hasta que el objeto se crea.

En resumen, los atributos de instancia son específicos de cada objeto, y cada instancia de la clase puede tener valores únicos para estos atributos.

## 1.5. Métodos

Un método, en el contexto de la programación orientada a objetos, se define como una función encapsulada dentro de una clase. Su propósito principal es modelar y simular un comportamiento específico asociado a la instancia de la clase. Por ejemplo, en una clase `Auto`, podría existir un método denominado `encender`, que representa la acción de poner en marcha el vehículo.

### 1.5.1. Métodos Estáticos

Los métodos estáticos pertenecen a la clase en sí misma y no a instancias particulares de la clase.

Se invocan directamente sobre la clase, prescindiendo de la necesidad de crear un objeto. Aunque es posible invocar métodos estáticos desde una instancia, no se considera una práctica recomendada.

Estos métodos tienen acceso exclusivo a los atributos estáticos, ya que no pueden acceder a instancias específicas.

### 1.5.2 Métodos de Instancia

Los métodos de instancia son esenciales y están vinculados a cada instancia en particular, no a la clase en su totalidad.

Solo pueden ser invocados por instancias de la clase y no directamente por la clase en sí.

Tienen la capacidad de acceder tanto a los atributos de instancia como a los atributos estáticos.

## 1.6. Paquetes

En programación, un paquete es un mecanismo que se utiliza para organizar y estructurar clases relacionadas dentro de un mismo espacio de nombres.

Los paquetes agrupan clases, interfaces, enumeraciones y otros paquetes de manera lógica y jerárquica, proporcionando una forma eficiente de evitar conflictos de nombres en proyectos grandes. De manera análoga, la estructura de un paquete refleja la organización de directorios en el sistema de archivos.
