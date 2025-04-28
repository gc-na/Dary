<!--
Meta Description: # Assert en Java: Comprobación de Condiciones en Tiempo de Ejecución ## Sinopsis El comando `assert` en Java se utiliza para realizar comprobaciones d...
Meta Keywords: que, assert, java, ser, condiciones
-->

# Assert en Java: Comprobación de Condiciones en Tiempo de Ejecución

## Sinopsis
El comando `assert` en Java se utiliza para realizar comprobaciones de condiciones en tiempo de ejecución, lo que permite a los desarrolladores verificar supuestos y detectar errores durante el desarrollo del programa.

## Documentación
La sentencia `assert` es una característica del lenguaje Java que se introdujo en Java 1.4. Su propósito principal es ayudar a los programadores a identificar errores lógicos en el código al permitirles establecer ciertas condiciones que deben ser verdaderas en un momento específico de la ejecución del programa. Si la condición evaluada es falsa, se lanza un error `AssertionError`.

### Uso
La sintaxis básica del comando `assert` es la siguiente:

```java
assert expresión_booleana;
```

También se puede utilizar una versión más explícita que permite proporcionar un mensaje de error personalizado:

```java
assert expresión_booleana : mensaje;
```

### Detalles
- Las afirmaciones están desactivadas por defecto en tiempo de ejecución, lo que significa que deben habilitarse al ejecutar el programa utilizando la opción `-ea` (o `-enableassertions`).
- Las afirmaciones no deben usarse para manejar condiciones de error que se espera que ocurran en la ejecución normal del programa. Su propósito es verificar condiciones que deberían ser verdaderas si el código se ha implementado correctamente.

## Ejemplos
### Ejemplo 1: Afirmación simple
```java
public class EjemploAfirmacion {
    public static void main(String[] args) {
        int valor = 5;
        assert valor > 0 : "El valor debe ser mayor que cero";
        System.out.println("El valor es positivo.");
    }
}
```

### Ejemplo 2: Afirmación con lógica compleja
```java
public class EjemploAfirmacionCompleja {
    public static void main(String[] args) {
        int numero = 10;
        assert numero % 2 == 0 : "El número debe ser par";
        System.out.println("El número es par.");
    }
}
```

## Explicación
Al utilizar `assert`, es importante tener en cuenta lo siguiente:
- **Desactivación por defecto**: Como se mencionó anteriormente, las afirmaciones están desactivadas de forma predeterminada. Esto significa que durante la fase de producción, las afirmaciones no se ejecutarán, por lo que no se debe depender de ellas para la lógica del programa.
- **Uso adecuado**: Las afirmaciones son herramientas para el desarrollo y la depuración. No deben ser utilizadas para manejar excepciones o condiciones que puedan ser esperadas durante la ejecución normal.
- **Rendimiento**: Debido a que las afirmaciones pueden ser desactivadas, no deberían ser utilizadas para la lógica crítica del programa, ya que su omisión podría llevar a comportamientos inesperados.

## Resumen en una línea
El comando `assert` en Java permite verificar condiciones en tiempo de ejecución, ayudando a los desarrolladores a identificar errores de lógica en su código.