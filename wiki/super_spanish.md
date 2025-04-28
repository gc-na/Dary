<!--
Meta Description: # Uso de "super" en Java: Comprendiendo su Funcionalidad y Aplicaciones ## Sinopsis La palabra clave "super" en Java se utiliza para referirse a la cl...
Meta Keywords: clase, padre, super, constructor, hijo
-->

# Uso de "super" en Java: Comprendiendo su Funcionalidad y Aplicaciones

## Sinopsis
La palabra clave "super" en Java se utiliza para referirse a la clase padre de un objeto. Permite acceder a métodos y variables de la clase base, facilitando la herencia y la reutilización del código.

## Documentación
### Propósito
La palabra clave "super" se emplea en el contexto de la programación orientada a objetos (POO) para acceder a atributos y métodos de la clase padre desde una clase hija. Esto es fundamental en la herencia, donde una clase puede extender la funcionalidad de otra.

### Uso
- **Acceder a métodos:** Puedes llamar a un método de la clase padre que ha sido sobrescrito en la clase hija.
- **Acceder a variables:** Permite acceder a las variables de instancia de la clase padre que pueden ser ocultadas en la clase hija.
- **Constructor de la clase padre:** Se usa para invocar el constructor de la clase padre desde el constructor de la clase hija.

### Detalles
- La palabra clave "super" se debe utilizar dentro de un constructor o método de la clase hija.
- Cuando se llama a un constructor de la clase padre con "super()", debe ser la primera línea del constructor de la clase hija.
- Si no se especifica un constructor de la clase padre, Java llama automáticamente al constructor por defecto.

## Ejemplos
### Ejemplo 1: Accediendo a un método de la clase padre
```java
class Padre {
    void mostrar() {
        System.out.println("Método de la clase Padre");
    }
}

class Hijo extends Padre {
    void mostrar() {
        super.mostrar(); // Llama al método de la clase Padre
        System.out.println("Método de la clase Hijo");
    }
}

public class Main {
    public static void main(String[] args) {
        Hijo obj = new Hijo();
        obj.mostrar();
    }
}
```

### Ejemplo 2: Usando "super" para acceder a una variable de instancia
```java
class Padre {
    String nombre = "Clase Padre";
}

class Hijo extends Padre {
    String nombre = "Clase Hijo";

    void mostrar() {
        System.out.println(super.nombre); // Accede a la variable de la clase Padre
    }
}

public class Main {
    public static void main(String[] args) {
        Hijo obj = new Hijo();
        obj.mostrar();
    }
}
```

### Ejemplo 3: Llamando al constructor de la clase padre
```java
class Padre {
    Padre() {
        System.out.println("Constructor de la clase Padre");
    }
}

class Hijo extends Padre {
    Hijo() {
        super(); // Llama al constructor de la clase Padre
        System.out.println("Constructor de la clase Hijo");
    }
}

public class Main {
    public static void main(String[] args) {
        Hijo obj = new Hijo();
    }
}
```

## Explicación
Es importante recordar que:
- Si la clase padre tiene un constructor que requiere parámetros, es necesario proporcionar esos argumentos al llamar a `super()`.
- No se puede utilizar "super" en un contexto estático, ya que no hay una instancia de objeto para referirse.
- El uso incorrecto de "super" puede llevar a confusiones, especialmente en jerarquías de herencia complejas.

## Resumen en una línea
La palabra clave "super" en Java permite a las clases hijas acceder a métodos, variables y constructores de su clase padre, facilitando la herencia en la programación orientada a objetos.