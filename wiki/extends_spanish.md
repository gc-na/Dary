<!--
Meta Description: # Extends en Java: La Clave para la Herencia en Programación Orientada a Objetos ## Sinopsis La palabra clave `extends` en Java se utiliza para establ...
Meta Keywords: una, extends, clase, java, que
-->

# Extends en Java: La Clave para la Herencia en Programación Orientada a Objetos

## Sinopsis
La palabra clave `extends` en Java se utiliza para establecer una relación de herencia entre clases. Permite que una clase (subclase) herede atributos y métodos de otra clase (superclase), promoviendo la reutilización de código y la creación de jerarquías de clases.

## Documentación
En Java, la herencia es un pilar fundamental de la programación orientada a objetos. La palabra clave `extends` se utiliza para crear una nueva clase que hereda propiedades y comportamientos de una clase existente. Esto significa que la subclase puede acceder a los métodos y atributos de la superclase, facilitando la creación de una aplicación más modular y mantenible.

### Propósito
El propósito principal de `extends` es permitir la creación de una nueva clase que pueda reutilizar el código de una clase existente, reduciendo la duplicación y mejorando la organización del código.

### Uso
Para utilizar `extends`, se declara una clase nueva seguida de la palabra clave `extends` y el nombre de la clase de la que se desea heredar. La sintaxis básica es la siguiente:

```java
class Subclase extends Superclase {
    // Cuerpo de la subclase
}
```
Es importante mencionar que Java no permite la herencia múltiple, es decir, una clase solo puede extender de una única superclase.

### Detalles
- La subclase hereda todos los métodos y atributos de la superclase, excepto los métodos y atributos privados.
- La subclase puede sobreescribir (override) los métodos de la superclase para modificar su comportamiento.
- Se puede utilizar la palabra clave `super` en la subclase para llamar al constructor o métodos de la superclase.

## Ejemplos

### Ejemplo 1: Herencia básica
```java
class Animal {
    void hacerSonido() {
        System.out.println("El animal hace un sonido");
    }
}

class Perro extends Animal {
    void hacerSonido() {
        System.out.println("El perro ladra");
    }
}

public class Main {
    public static void main(String[] args) {
        Perro miPerro = new Perro();
        miPerro.hacerSonido(); // Salida: El perro ladra
    }
}
```

### Ejemplo 2: Uso de `super`
```java
class Vehiculo {
    Vehiculo() {
        System.out.println("Un vehiculo ha sido creado");
    }
}

class Coche extends Vehiculo {
    Coche() {
        super(); // Llama al constructor de Vehiculo
        System.out.println("Un coche ha sido creado");
    }
}

public class Main {
    public static void main(String[] args) {
        Coche miCoche = new Coche();
        // Salida:
        // Un vehiculo ha sido creado
        // Un coche ha sido creado
    }
}
```

## Explicación
Al utilizar `extends`, es fundamental entender que la subclase hereda no solo los métodos y atributos, sino también la estructura y las características de la superclase. Algunos errores comunes incluyen:

- **Sobrescribir métodos sin usar `@Override`**: Aunque Java permite sobrescribir métodos sin esta anotación, su uso es recomendable para mejorar la legibilidad y detectar errores en tiempo de compilación.
- **Intentar heredar múltiples clases**: Java no soporta herencia múltiple, por lo que se debe tener cuidado al estructurar jerarquías de clases.

Además, es importante recordar que la herencia puede aumentar la complejidad del código si no se gestiona adecuadamente, por lo que se debe usar con precaución.

## Resumen en una Línea
La palabra clave `extends` en Java permite a una clase heredar atributos y métodos de otra clase, facilitando la reutilización de código y la estructuración de jerarquías de clases.