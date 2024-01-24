## 7.1. POJO

Un POJO (Plain Old Java Object), es un termino utilizado en la programación con Java para describir un objeto Java simple y ordinario que se adhiere a ciertas convenciones y no se apoya de un framework o tecnología específica. El concepto de POJO está asociado con la simplicidad, fácil mantenimiento, e independencia de frameworks complejos, haciéndolo versátil y ampliamente aplicable.

Aquí hay algunas características claves y explicaciones relacionadas a POJO:

- **Plain Old Java Object (POJO):**

  - **Definición:** Un POJO es una clase Java que no depende de un framework, librería, o tecnología externa. Se adhiere a convenciones Java básicas y no está atado a requerimientos específicos impuestos por frameworks como Java EE, Spring, o Hibernate.

  - **Propósito:** POJOs están diseñados para ser simples, fáciles de entender, y libres de dependencias y frameworks especializados. Promueven programación Java limpia y directa, haciendo el código más mantenible y adaptable.

- **Características de un POJO:**

  - **No dependencia de frameworks:** Un POJO no debería basarse en un framework específico o tecnología. Debería ser independiente.
  - **Serializable:** Mientras no es estrictamente requerido, muchos POJOs implementan una interfaz "**Serializable**" para soportar serialización y deserialización.
  - **Convenciones Java estándar:** Sigue convenciones de nombrado estándar de Java para métodos, campos, y paquetes. Evita utilizar anotaciones específicas de un framework o herencia.

**Ejemplo de un POJO**

```java
public class Person {
    private String name;
    private int age;

    // Constructors
    public Person() {
    }

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // Getter and Setter methods
    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}

```
