<!--
Meta Description: # Uso del comando "do" en JAVA: Sintaxis y Ejemplos ## Sinopsis El comando `do` en JAVA se utiliza en la estructura de control de bucles, específicame...
Meta Keywords: que, una, bucle, while, condición
-->

# Uso del comando "do" en JAVA: Sintaxis y Ejemplos

## Sinopsis
El comando `do` en JAVA se utiliza en la estructura de control de bucles, específicamente en el bucle `do-while`, que permite ejecutar un bloque de código al menos una vez antes de evaluar una condición.

## Documentación
El bucle `do-while` es una de las estructuras de control de flujo en JAVA que permite la ejecución repetida de un bloque de código mientras se cumpla una condición. A diferencia del bucle `while`, en el que la condición se verifica antes de ejecutar el bloque, el bucle `do-while` garantiza que el bloque de código se ejecute al menos una vez.

### Sintaxis
```java
do {
    // Bloque de código a ejecutar
} while (condición);
```

### Propósito
El propósito del bucle `do-while` es permitir la ejecución de código repetidamente con la certeza de que se ejecutará al menos una vez, independientemente de si la condición inicial es verdadera o falsa.

### Uso
El bucle `do-while` se utiliza comúnmente en situaciones donde se desea que el usuario realice una acción al menos una vez, como en menús interactivos, validaciones de entrada, o para realizar tareas repetitivas que requieren al menos una ejecución inicial.

## Ejemplos

### Ejemplo 1: Bucle simple
```java
int i = 0;
do {
    System.out.println("El valor de i es: " + i);
    i++;
} while (i < 5);
```
**Salida:**
```
El valor de i es: 0
El valor de i es: 1
El valor de i es: 2
El valor de i es: 3
El valor de i es: 4
```

### Ejemplo 2: Validación de entrada del usuario
```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int numero;

        do {
            System.out.print("Introduce un número positivo: ");
            numero = scanner.nextInt();
        } while (numero <= 0);
        
        System.out.println("Has introducido el número positivo: " + numero);
        scanner.close();
    }
}
```

## Explicación
Un error común al usar el bucle `do-while` es olvidar actualizar la variable de control, lo que puede llevar a un bucle infinito. Además, es importante recordar que la condición se evalúa después de la ejecución del bloque de código, lo que implica que siempre se ejecutará al menos una vez.

### Gotchas
- **Condiciones falsas:** Si la condición es siempre falsa (por ejemplo, `while (false)`), el bucle se ejecutará solo una vez.
- **Bucle infinito:** Si no se modifica la variable que afecta la condición, se puede generar un bucle infinito, que puede causar que el programa se congele.

## Resumen en una línea
El comando `do` en JAVA permite ejecutar un bloque de código al menos una vez, seguido de una condición, en el contexto del bucle `do-while`.