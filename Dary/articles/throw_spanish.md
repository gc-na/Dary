<!--
Meta Description: # Uso de "throw" en JAVA: Manejo de Excepciones ## Sinopsis El comando "throw" en JAVA se utiliza para lanzar excepciones de manera explícita, permiti...
Meta Keywords: throw, que, excepciones, ser, java
-->

# Uso de "throw" en JAVA: Manejo de Excepciones

## Sinopsis
El comando "throw" en JAVA se utiliza para lanzar excepciones de manera explícita, permitiendo a los desarrolladores gestionar errores y condiciones excepcionales en sus aplicaciones.

## Documentación
El propósito de "throw" es permitir que un programa interrumpa su flujo normal de ejecución y transfiera el control a un bloque de manejo de excepciones. Esto es fundamental en la programación orientada a objetos, ya que permite a los desarrolladores definir y manejar errores personalizados.

### Uso
La sintaxis básica del comando "throw" es la siguiente:

```java
throw new ExceptionType("Mensaje de error");
```

- **ExceptionType**: puede ser cualquier clase que extienda de `Throwable`, como `Exception` o `RuntimeException`.
- **Mensaje de error**: una cadena que proporciona información sobre el error que ocurrió.

### Detalles
- "throw" se utiliza dentro de métodos y puede lanzar excepciones que deben ser manejadas por el código que llama al método.
- Las excepciones lanzadas pueden ser verificadas (checked) o no verificadas (unchecked). Las excepciones verificadas deben ser declaradas en la firma del método usando `throws`, mientras que las no verificadas no requieren esta declaración.

## Ejemplos
### Ejemplo 1: Lanzar una excepción verificada

```java
public void validarEdad(int edad) throws IllegalArgumentException {
    if (edad < 18) {
        throw new IllegalArgumentException("La edad debe ser al menos 18 años.");
    }
    System.out.println("Edad válida.");
}
```

### Ejemplo 2: Lanzar una excepción no verificada

```java
public void dividir(int numerador, int denominador) {
    if (denominador == 0) {
        throw new ArithmeticException("No se puede dividir por cero.");
    }
    System.out.println("El resultado es: " + (numerador / denominador));
}
```

## Explicación
Al usar "throw", es importante tener en cuenta algunos puntos:

- **Bloques try-catch**: Cuando se lanza una excepción, debe ser capturada y manejada apropiadamente mediante bloques `try-catch` para evitar que el programa termine abruptamente.
- **Propagación de excepciones**: Si una excepción no es manejada en el método en el que se lanza, se propagará hacia arriba en la pila de llamadas hasta ser capturada o causar la finalización del programa.
- **Mensajes de error claros**: Al lanzar excepciones, es recomendable proporcionar mensajes de error claros y específicos para facilitar el diagnóstico de problemas.

## Resumen en una línea
El comando "throw" en JAVA permite lanzar excepciones personalizadas para gestionar errores y condiciones excepcionales en la programación.