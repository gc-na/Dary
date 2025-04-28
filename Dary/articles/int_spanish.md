<!--
Meta Description: # int en Java: Todo lo que Necesitas Saber ## Sinopsis El tipo de dato `int` en Java es un entero de 32 bits con signo que se utiliza para representar...
Meta Keywords: int, java, que, system, out
-->

# int en Java: Todo lo que Necesitas Saber

## Sinopsis
El tipo de dato `int` en Java es un entero de 32 bits con signo que se utiliza para representar números enteros en aplicaciones. Es uno de los tipos primitivos más comunes y fundamentales en la programación Java.

## Documentación
En Java, `int` es uno de los ocho tipos de datos primitivos que permite almacenar valores numéricos enteros. Su rango va desde -2,147,483,648 hasta 2,147,483,647. Esto lo hace adecuado para una amplia gama de aplicaciones, desde cálculos simples hasta operaciones complejas en estructuras de datos.

### Uso
Para declarar una variable de tipo `int`, se utiliza la siguiente sintaxis:
```java
int nombreVariable;
```
Puedes inicializarla al momento de la declaración:
```java
int edad = 25;
```

Además, `int` puede ser utilizado en operaciones aritméticas, comparaciones y más. A continuación se presentan algunas de las operaciones más comunes que puedes realizar con `int`:

- Suma: `int suma = a + b;`
- Resta: `int resta = a - b;`
- Multiplicación: `int multiplicacion = a * b;`
- División: `int division = a / b;`
- Módulo: `int modulo = a % b;`

## Ejemplos
### Ejemplo 1: Declaración y Asignación
```java
int numero = 10;
System.out.println("El número es: " + numero);
```

### Ejemplo 2: Operaciones Aritméticas
```java
int a = 15;
int b = 4;
int suma = a + b;
int resta = a - b;
int multiplicacion = a * b;
int division = a / b;
int modulo = a % b;

System.out.println("Suma: " + suma);
System.out.println("Resta: " + resta);
System.out.println("Multiplicación: " + multiplicacion);
System.out.println("División: " + division);
System.out.println("Módulo: " + modulo);
```

### Ejemplo 3: Uso en Condicionales
```java
int edad = 18;
if (edad >= 18) {
    System.out.println("Eres mayor de edad.");
} else {
    System.out.println("Eres menor de edad.");
}
```

## Explicación
Al trabajar con `int`, es importante tener en cuenta el rango de valores. Si intentas almacenar un valor que excede el rango permitido, obtendrás un error de compilación o un comportamiento inesperado (overflow).

Otro aspecto a considerar es que las operaciones entre enteros pueden resultar en truncamiento si el resultado excede el rango de `int`. Por ejemplo, la división de dos enteros siempre producirá un entero, descartando la parte decimal.

Es recomendable utilizar el tipo `long` si esperas trabajar con números enteros que puedan exceder el límite de `int`.

## Resumen en una Frase
El tipo de dato `int` en Java es un entero de 32 bits que permite realizar operaciones matemáticas y lógicas con números enteros en aplicaciones.