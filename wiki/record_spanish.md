<!--
Meta Description: # Uso de "record" en Java: Características y Ejemplos ## Sinopsis Los "record" en Java son una nueva característica introducida en Java 14 como una fo...
Meta Keywords: record, que, los, java, clases
-->

# Uso de "record" en Java: Características y Ejemplos

## Sinopsis
Los "record" en Java son una nueva característica introducida en Java 14 como una forma de definir clases inmutables de manera más concisa y legible. Permiten crear clases que son esencialmente contenedores para datos, facilitando la programación funcional y la creación de objetos simples.

## Documentación
### Propósito
El propósito principal de los "record" en Java es simplificar la creación de clases que solo contienen datos, eliminando la necesidad de escribir manualmente el código repetitivo asociado a las clases tradicionales, como constructores, métodos `equals()`, `hashCode()` y `toString()`.

### Uso
Para declarar un "record", se utiliza la palabra clave `record` seguida del nombre del "record" y la lista de sus componentes entre paréntesis. Un "record" se comporta como una clase final, lo que significa que no puede ser extendido.

#### Sintaxis básica
```java
public record NombreRecord(tipo componente1, tipo componente2, ...) {}
```

### Detalles
- **Inmutabilidad**: Los campos de un "record" son automáticamente finales, lo que significa que su valor no puede cambiar después de la creación del objeto.
- **Generación automática**: El compilador genera automáticamente métodos `equals()`, `hashCode()` y `toString()` basados en los componentes definidos.
- **Desestructuración**: Se puede acceder a los componentes de un "record" mediante métodos de acceso generados automáticamente, que tienen el mismo nombre que cada componente.

## Ejemplos
### Ejemplo 1: Declaración básica de un record
```java
public record Persona(String nombre, int edad) {}
```

### Ejemplo 2: Uso de un record
```java
public class Main {
    public static void main(String[] args) {
        Persona p1 = new Persona("Juan", 25);
        System.out.println(p1.nombre()); // Salida: Juan
        System.out.println(p1.edad());   // Salida: 25
        
        System.out.println(p1); // Salida: Persona[nombre=Juan, edad=25]
    }
}
```

### Ejemplo 3: Comparación de records
```java
public class Main {
    public static void main(String[] args) {
        Persona p1 = new Persona("Ana", 30);
        Persona p2 = new Persona("Ana", 30);
        System.out.println(p1.equals(p2)); // Salida: true
    }
}
```

## Explicación
Al utilizar "records", es esencial recordar que se trata de clases inmutables. Esto puede causar problemas si se intenta modificar los valores de los componentes después de la creación del objeto. Además, al ser clases finales, no se pueden extender, lo que puede limitar la flexibilidad en ciertos casos.

Una trampa común es intentar añadir métodos adicionales que alteren el estado del "record", lo que no es posible dado que los componentes son finales. También es importante tener en cuenta que, aunque los records simplifican mucho la definición de clases de datos, no son adecuados para todas las situaciones, especialmente cuando se requiere herencia o comportamiento mutable.

## Resumen en una línea
Los "record" en Java son una forma concisa y segura de definir clases inmutables que contienen datos, simplificando el desarrollo y la legibilidad del código.