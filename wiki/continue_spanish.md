<!--
Meta Description: # Uso de la instrucción "continue" en Java: Guía Completa ## Sinopsis La instrucción `continue` en Java se utiliza dentro de bucles para omitir la ite...
Meta Keywords: continue, bucle, iteración, instrucción, java
-->

# Uso de la instrucción "continue" en Java: Guía Completa

## Sinopsis
La instrucción `continue` en Java se utiliza dentro de bucles para omitir la iteración actual y pasar directamente a la siguiente. Esta característica es útil para controlar el flujo de ejecución en situaciones donde se desea evitar la ejecución de ciertas partes del código bajo condiciones específicas.

## Documentación
La instrucción `continue` se emplea en bucles `for`, `while` y `do-while`. Su propósito es interrumpir la iteración actual sin salir del bucle, permitiendo que el programa continúe con la próxima iteración.

### Propósito
La instrucción `continue` es especialmente útil cuando se necesita saltar algunas condiciones sin interrumpir completamente el bucle. Por ejemplo, en un bucle que itera sobre una colección de elementos, puedes usar `continue` para evitar procesar elementos que no cumplen ciertos criterios.

### Uso
La sintaxis básica de `continue` en Java es:

```java
continue;
```

En el caso de bucles anidados, se puede utilizar `continue` con una etiqueta para especificar a qué bucle se debe aplicar.

### Ejemplo de uso
Aquí hay un ejemplo simple que demuestra cómo se utiliza la instrucción `continue`:

```java
public class EjemploContinue {
    public static void main(String[] args) {
        for (int i = 1; i <= 10; i++) {
            if (i % 2 == 0) {
                continue; // Salta los números pares
            }
            System.out.println(i); // Imprime números impares
        }
    }
}
```

### Resultado:
Este código imprimirá:
```
1
3
5
7
9
```

## Explicación
### Errores comunes y notas
1. **Uso incorrecto en bucles no adecuados**: La instrucción `continue` solo tiene sentido dentro de bucles. Si se intenta utilizar fuera de un bucle, se generará un error de compilación.
   
2. **Confusión con `break`**: Es importante no confundir `continue` con `break`. Mientras que `break` termina el bucle completamente, `continue` solo salta a la siguiente iteración.

3. **Bucles anidados**: Cuando se trabaja con bucles anidados, es posible que se necesite usar etiquetas para especificar cuál bucle debe continuar. Si no se hace correctamente, puede resultar confuso y puede que no se obtengan los resultados esperados.

```java
outerLoop:
for (int i = 1; i <= 5; i++) {
    for (int j = 1; j <= 5; j++) {
        if (j == 3) {
            continue outerLoop; // Salta a la siguiente iteración del bucle externo
        }
        System.out.println("i: " + i + ", j: " + j);
    }
}
```

En este caso, cuando `j` es igual a 3, se salta a la siguiente iteración del bucle externo.

## Resumen en una línea
La instrucción `continue` en Java permite omitir la ejecución del código restante en la iteración actual de un bucle, continuando con la siguiente iteración.