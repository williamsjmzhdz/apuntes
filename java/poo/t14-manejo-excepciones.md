# 14.1 Manejo de excepciones

El manejo de excepciones y errores en Java es una parte fundamental de escribir código robusto y fiable. Las excepciones son situaciones que alteran el flujo normal de un programa, y Java proporciona un mecanismo robusto para manejarlas de manera controlada.

## 14.1.1. Tipos de excepciones en Java

- **Checked Exceptions**: Excepciones que son comprobadas en tiempo de compilación. Son situaciones de las que el programa podría recuperarse. Ejemplos: '**IOException**', '**SQLException**'.

- **Unchecked Exceptions**: No son comprobadas en tiempo de compilación. Incluyen errores de lógico que los programas no deberían intentar recuperarse. Se dividen en:

  - **Errores**: Problemas graves que no deberían ser manejados por la aplicación. Ejemplos: '**OutOfMemoryError**', '**StackOverflowError**'.
  - **Runtime Exceptions**: Errores de programación que podrían haberse evitado. Ejemplos: '**NullPointerException**', '**IndexOutOfBounceException**'.

## 14.1.2. Manejo de excepciones

Java utiliza los bloques '**try**', '**catch**', '**finally**', y la palabra clave '**throw**' para manejar excepciones:

- '**try**': Bloque que encierra el código que podría lanzar una excepción
- '**catch**': Captura y maneja las excepciones especificadas. Puedes tener múltiples bloques '**catch**' para diferentes tipos de excepciones.
- '**finally**': Se ejecuta después de los bloques '**try**' y '**catch**', independientemente de si se lanzó una excepción. Útil para limpieza.
- '**throw**': Usado para lanzar una excepción explicitamente.

## 14.1.3. Buenas prácticas para el manejo de excepciones

- Manejar solo las excepciones que puedes recuperar o cuando necesitas realizar acciones específicas como resultado.
- Evitar el uso excesivo del bloque try-catch para controlar la lógica del programa.
- Usar bloques '**finally**' o '**try-with-resources**' para asegurar que los recursos se liberen correctamente.
- Proporcionar mensajes de error útiles e información de depuración en los bloques '**catch**'

## 14.1.4. Ejemplo práctico

```java
import java.io.FileReader;
import java.io.BufferedReader;
import java.io.FileNotFoundException;
import java.io.IOException;

public class FileReader {
  public static void main(String[] args) {
    BufferedReader reader = null;
    try {
      reader = new BufferedReader(new FileReader("example.txt"));
      String line = null;
      while ((line = reader.readLine()) != null) {
        System.out.println(line);
      }
    } catch (FileNotFoundException e) {
      System.out.println("El archivo no fue encontrado: " + e.getMessage());
    } catch (IOException e) {
      System.out.println("Error al leer el archivo: " + e.getMessage());
    } finally {
      try {
        if (reader != null) reader.close();
      } catch (IOException e) {
        System.out.println("Error al cerrar el archivo: " + e.getMessage());
      }
    }
  }
}
```

En este ejemplo utilizamos FileReader y BufferedReader para leer un archivo línea por línea. Manejamos FileNotFoundException para el caso de que el archivo no exista y IOException para errores de lectura. Independientemente de si se producen estas excepciones, el bloque finally asegura que el archivo se cierre correctamente, manejando también cualquier IOException que pueda ocurrir al cerrar.

Este ejemplo muestra cómo manejar adecuadamente varias excepciones específicas, garantizando que los recursos se gestionen correctamente y proporcionando mensajes de error informativos para facilitar la depuración.
