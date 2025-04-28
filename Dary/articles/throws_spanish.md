<!--
Meta Description: # Uso de "throws" en JAVA: Manejo de Excepciones ## Sinopsis El comando `throws` en Java se utiliza en la declaración de métodos para indicar que este...
Meta Keywords: que, método, throws, excepciones, java
-->

# Uso de "throws" en JAVA: Manejo de Excepciones

## Sinopsis
El comando `throws` en Java se utiliza en la declaración de métodos para indicar que este método puede lanzar excepciones específicas, permitiendo a los desarrolladores manejar errores de manera controlada.

## Documentación
El uso de `throws` es fundamental en el manejo de excepciones en Java. Cuando un método puede generar una excepción que no maneja internamente, se debe declarar con la palabra clave `throws`, seguida de la(s) excepción(es) que puede lanzar. Esto permite que el método que llama a este método sepa que debe manejar la excepción, ya sea capturándola con un bloque `try-catch` o propagándola a su vez.

### Propósito
El propósito principal de `throws` es proporcionar una forma de informar a los usuarios de un método sobre las excepciones que pueden ocurrir, permitiendo una gestión más robusta y predecible de errores.

### Uso
La sintaxis básica para declarar un método que puede lanzar excepciones es la siguiente:

```java
modificador_de_acceso tipo_de_retorno nombreDelMétodo(parametros) throws TipoDeExcepción1, TipoDeExcepción2 {
    // Cuerpo del método
}
```

### Detalles
- **Modificadores de acceso**: Pueden ser `public`, `private`, etc.
- **Tipo de retorno**: Puede ser cualquier tipo de dato, incluyendo `void`.
- **Nombre del método**: Debe seguir las convenciones de nomenclatura de Java.
- **Parámetros**: Los parámetros del método que pueden ser necesarios para su ejecución.
- **Tipo de Excepción**: Puede ser cualquier excepción que extienda de `Throwable`, como `IOException`, `SQLException`, etc.

## Ejemplos
### Ejemplo 1: Método que lanza una excepción comprobada

```java
public void leerArchivo(String nombreArchivo) throws IOException {
    FileReader archivo = new FileReader(nombreArchivo);
    // Lógica para leer el archivo
}
```

### Ejemplo 2: Método que maneja excepciones lanzadas

```java
public void procesarArchivo(String nombreArchivo) {
    try {
        leerArchivo(nombreArchivo);
    } catch (IOException e) {
        System.out.println("Error al leer el archivo: " + e.getMessage());
    }
}
```

## Explicación
Un error común al utilizar `throws` es no capturar adecuadamente las excepciones en el método que llama. Si se ignora la excepción, el programa puede terminar abruptamente. Además, es importante recordar que `throws` solo se utiliza para excepciones comprobadas. Las excepciones no comprobadas (como `NullPointerException`) no necesitan ser declaradas.

Otra trampa común es confundir `throws` con `throw`. `throw` se utiliza para lanzar una excepción de manera explícita, mientras que `throws` se utiliza para declarar que un método puede lanzar excepciones.

## Resumen en Una Línea
El comando `throws` en Java permite a los métodos indicar que pueden lanzar excepciones específicas, facilitando el manejo de errores en la programación.