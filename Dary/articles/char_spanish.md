<!--
Meta Description: # Char en Java: Tipos de Datos y Uso ## Sinopsis El tipo de dato `char` en Java representa un único carácter Unicode en un formato de 16 bits. Es fund...
Meta Keywords: char, java, caracteres, tipo, carácter
-->

# Char en Java: Tipos de Datos y Uso

## Sinopsis
El tipo de dato `char` en Java representa un único carácter Unicode en un formato de 16 bits. Es fundamental para la manipulación de texto y se utiliza en diversas aplicaciones de programación.

## Documentación
El tipo `char` se utiliza en Java para almacenar caracteres individuales. Cada `char` en Java es un valor de 16 bits que puede representar cualquier carácter en el conjunto de caracteres Unicode, lo que permite la representación de caracteres de múltiples lenguas y símbolos.

### Propósito
El propósito principal del tipo `char` es almacenar un solo carácter. Esto es útil en situaciones donde necesitas trabajar con texto, como en la construcción de cadenas o en la manipulación de datos de entrada del usuario.

### Uso
Para declarar una variable de tipo `char`, se utiliza la siguiente sintaxis:

```java
char letra = 'A';
```

Los caracteres se delimitan con comillas simples. También es posible asignar valores numéricos a un `char`, que corresponden a su valor Unicode. Por ejemplo:

```java
char letra = 65; // A en Unicode
```

### Detalles
- El rango de valores que puede tomar un `char` es de `'\u0000'` (0) a `'\uffff'` (65535).
- Se pueden utilizar secuencias de escape para representar caracteres especiales, como `'\n'` para nueva línea o `'\t'` para tabulación.

## Ejemplos
A continuación se presentan algunos ejemplos básicos del uso del tipo `char` en Java:

```java
public class EjemploChar {
    public static void main(String[] args) {
        char letra = 'J';
        System.out.println("El carácter es: " + letra);

        char numero = 50; // Representa el carácter '2'
        System.out.println("El carácter correspondiente al número 50 es: " + numero);

        char nuevaLinea = '\n';
        System.out.print("Primera línea" + nuevaLinea + "Segunda línea");
    }
}
```

## Explicación
Un error común al trabajar con el tipo `char` es confundirlo con el tipo `String`. Mientras que `char` representa un solo carácter, `String` representa una secuencia de caracteres. Por ejemplo:

```java
char c = 'A'; // Correcto
String s = "A"; // Correcto, pero es una cadena, no un carácter
```

Otro aspecto a considerar es que los caracteres Unicode en Java incluyen no solo caracteres alfabéticos, sino también símbolos y caracteres de control, lo que puede llevar a confusiones si no se manejan adecuadamente.

## Resumen en una línea
El tipo de dato `char` en Java permite almacenar caracteres individuales en formato Unicode, facilitando la manipulación de texto en aplicaciones.