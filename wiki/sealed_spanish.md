<!--
Meta Description: # Cláusula Sealed en JAVA: Controlando la Herencia de Clases ## Sinopsis La cláusula `sealed` en JAVA es una característica introducida en Java 15 que...
Meta Keywords: clase, que, clases, sealed, una
-->

# Cláusula Sealed en JAVA: Controlando la Herencia de Clases 

## Sinopsis
La cláusula `sealed` en JAVA es una característica introducida en Java 15 que permite restringir la herencia de clases y mejorar el control sobre las jerarquías de clases. Esta funcionalidad es útil para crear una arquitectura más predecible y segura en aplicaciones grandes.

## Documentación
La cláusula `sealed` se utiliza para declarar una clase o interfaz que no puede ser heredada por cualquier otra clase a menos que se especifique explícitamente. Esto significa que puedes definir qué clases pueden extender una clase sellada, ofreciendo un control más estricto sobre la herencia.

### Propósito
El propósito principal de `sealed` es proporcionar un mecanismo para limitar las subclases de una clase o interfaz, permitiendo que solo un conjunto específico de clases extiendan o implementen el comportamiento. Esto se traduce en un diseño más robusto y fácil de mantener.

### Uso
Para declarar una clase o interfaz como `sealed`, se utiliza la palabra clave `sealed` seguida de `permits` para listar las subclases permitidas. Aquí tienes un ejemplo básico:

```java
sealed class Vehiculo permits Coche, Moto {
    // Implementación de la clase Vehiculo
}

final class Coche extends Vehiculo {
    // Implementación de la clase Coche
}

final class Moto extends Vehiculo {
    // Implementación de la clase Moto
}
```

En este ejemplo, `Vehiculo` es una clase sellada que solo permite que `Coche` y `Moto` la extiendan. Las clases `Coche` y `Moto` son marcadas como `final`, lo que significa que no pueden ser heredadas nuevamente.

## Ejemplos
### Ejemplo 1: Definición de una clase sellada
```java
sealed class Animal permits Perro, Gato {
    // Métodos y atributos de la clase Animal
}

final class Perro extends Animal {
    // Implementación de la clase Perro
}

final class Gato extends Animal {
    // Implementación de la clase Gato
}
```

### Ejemplo 2: Uso de interfaces selladas
```java
sealed interface Forma permits Circulo, Cuadrado {
    double area();
}

final class Circulo implements Forma {
    private double radio;

    public Circulo(double radio) {
        this.radio = radio;
    }

    public double area() {
        return Math.PI * radio * radio;
    }
}

final class Cuadrado implements Forma {
    private double lado;

    public Cuadrado(double lado) {
        this.lado = lado;
    }

    public double area() {
        return lado * lado;
    }
}
```

## Explicación
### Problemas Comunes
Al utilizar clases selladas, es importante recordar que:
- No puedes extender una clase sellada desde una clase que no esté permitida en la declaración `permits`.
- Las clases permitidas deben ser declaradas como `final` o también selladas, si deseas permitir que otras clases las extiendan.
- Las interfaces selladas tienen un funcionamiento similar, pero debes asegurarte de que todas las implementaciones respeten la jerarquía definida.

### Notas Adicionales
La cláusula `sealed` es especialmente útil en el diseño de API y bibliotecas, donde se desea mantener un control estricto sobre cómo se utilizan las clases y evitar herencias no deseadas que puedan romper la lógica del programa.

## Resumen en Una Línea
La cláusula `sealed` en JAVA permite restringir la herencia de clases, mejorando el control sobre las jerarquías de clases y promoviendo un diseño más seguro y predecible.