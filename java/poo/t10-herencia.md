# 10.1. Herencia

Es un concepto fundamental y uno de los cuatro pilares de la programación orientada a objetos. Este concepto permite a una clase heredar propiedades y comportamientos de otra clase. La herencia facilita la creación de nuevas clases basadas en clases existentes, permitiendo la reutilización de código y la extensión de funcionalidades.

Una clase que es derivada de otra clase es llamada subclase (también clase derivada, clase extendida o clase hija). La clase de la cuál la subclase es derivada es llamada superclase (también clase base o clase padre).

Exceptuando _Object_, la cual no tiene superclase, cada clase tiene una y solo una superclase directa (herencia simple). En ausencia de cualquier superclase explícita, cada clase es implícitamente una subclase de _Object_.

Las clases pueden ser derivadas de clases que son derivadas de clases que son derivadas de clases, y así sucesivamente, y finalmente derivadas de la clase superior, _Object_. Así por lo tanto, se dice que una clase desciende de todas las clases en la cadena de herencia que se extiende hacia atrás, hasta la clase _Object_.
