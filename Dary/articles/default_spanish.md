<!--
Meta Description: # Default en Java: Comprendiendo el Modificador de Acceso y Métodos por Defecto ## Sinopsis El término "default" en Java se refiere a un modificador d...
Meta Keywords: por, defecto, acceso, métodos, java
-->

# Default en Java: Comprendiendo el Modificador de Acceso y Métodos por Defecto

## Sinopsis
El término "default" en Java se refiere a un modificador de acceso que permite la visibilidad de clases, métodos y variables dentro del mismo paquete. También se utiliza en las interfaces para declarar métodos que tienen una implementación por defecto.

## Documentación
En Java, el modificador de acceso "default" se utiliza en dos contextos principales:

1. **Modificador de Acceso por Defecto**: Cuando no se especifica un modificador de acceso (como `public`, `protected` o `private`), el acceso por defecto permite que las clases, métodos y variables sean accesibles solo dentro del mismo paquete. Este es el comportamiento predeterminado cuando no se declara otro modificador.

2. **Métodos por Defecto en Interfaces**: Introducido en Java 8, los métodos por defecto permiten a los programadores agregar nuevos métodos a las interfaces sin romper las clases que ya implementan esa interfaz. Se declaran utilizando la palabra clave `default` seguida de la implementación del método. Esto permite el uso de métodos con comportamiento predeterminado en interfaces.

### Uso del Modificador de Acceso por Defecto
- **Clases y Métodos**: Si no se especifica un modificador de acceso, el acceso es por defecto.
  ```java
  class MiClase {
      void miMetodo() {
          // Acceso por defecto
      }
  }
  ```

### Uso de Métodos por Defecto en Interfaces
- **Declaración de Métodos por Defecto**:
  ```java
  interface MiInterfaz {
      default void metodoPorDefecto() {
          System.out.println("Este es un método por defecto.");
      }
  }
  ```

## Ejemplos
### Ejemplo de Modificador de Acceso por Defecto
```java
// Archivo: MiClase.java
class MiClase {
    void metodo() {
        System.out.println("Método de acceso por defecto.");
    }
}

// Archivo: MiClaseDePrueba.java
public class MiClaseDePrueba {
    public static void main(String[] args) {
        MiClase objeto = new MiClase();
        objeto.metodo(); // Acceso permitido dentro del mismo paquete
    }
}
```

### Ejemplo de Método por Defecto en una Interfaz
```java
interface Animal {
    default void sonido() {
        System.out.println("El animal hace un sonido.");
    }
}

class Perro implements Animal {
    // Puede usar el método por defecto o sobreescribirlo
}

public class Main {
    public static void main(String[] args) {
        Perro perro = new Perro();
        perro.sonido(); // Imprime: "El animal hace un sonido."
    }
}
```

## Explicación
Al utilizar el modificador de acceso por defecto, es importante recordar que solo se puede acceder a los elementos dentro del mismo paquete. Esto puede llevar a confusiones si se intenta acceder a una clase o método por defecto desde otro paquete, resultando en un error de compilación.

Con respecto a los métodos por defecto en las interfaces, un punto común de confusión es su uso en clases que implementan múltiples interfaces. Si dos interfaces tienen métodos por defecto con el mismo nombre, la clase que los implementa debe proporcionar su propia implementación del método para evitar ambigüedades.

## Resumen en Una Frase
El modificador "default" en Java permite la visibilidad dentro del paquete y la implementación de métodos por defecto en interfaces, facilitando la evolución de las APIs sin romper la compatibilidad.