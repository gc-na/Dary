<!--
Meta Description: # Non-Sealed en Java: Comprendiendo el Modificador de Clases ## Sinopsis El modificador `non-sealed` en Java se utiliza para indicar que una clase sel...
Meta Keywords: sealed, non, que, una, clases
-->

# Non-Sealed en Java: Comprendiendo el Modificador de Clases

## Sinopsis
El modificador `non-sealed` en Java se utiliza para indicar que una clase sellada (sealed class) puede ser extendida sin restricciones por otras clases, permitiendo una mayor flexibilidad en la jerarquía de herencia.

## Documentación
En Java, a partir de la versión 15, se introdujo el concepto de clases selladas (`sealed classes`), que permiten a los desarrolladores controlar qué clases pueden extenderlas. Las clases selladas son una herramienta útil para crear jerarquías de clases más controladas y seguras. 

El modificador `non-sealed` se utiliza dentro del contexto de una clase sellada para permitir que ciertas subclases se extiendan sin restricciones. Esto significa que, aunque una clase padre esté sellada, las clases que se marcan como `non-sealed` podrán ser heredadas por cualquier clase, sin importar su relación con la jerarquía de clases selladas.

### Propósito
El propósito de `non-sealed` es ofrecer un equilibrio entre el control que proporciona una clase sellada y la flexibilidad que requiere el desarrollo de ciertas aplicaciones. Permite a los desarrolladores definir subclases que pueden ser utilizadas libremente, incluso dentro de un contexto sellado.

### Uso
Para usar `non-sealed`, primero debes declarar una clase como sellada utilizando el modificador `sealed`. Luego, puedes marcar una subclase específica con el modificador `non-sealed`. A continuación se muestra la sintaxis:

```java
sealed class ClaseSellada permits ClaseSellada1, ClaseSellada2 {
}

non-sealed class ClaseSellada1 extends ClaseSellada {
}

class ClaseSellada2 extends ClaseSellada {
}
```

## Ejemplos
### Ejemplo Básico

```java
sealed class Vehiculo permits Coche, Motocicleta {
}

non-sealed class Coche extends Vehiculo {
    // Implementación específica de Coche
}

class Motocicleta extends Vehiculo {
    // Implementación específica de Motocicleta
}
```

En este ejemplo, `Vehiculo` es una clase sellada que permite a `Coche` y `Motocicleta` ser sus subclases. `Coche` se marca como `non-sealed`, lo que significa que puede ser extendido por otras clases, mientras que `Motocicleta` no tiene esa opción.

## Explicación
### Problemas Comunes y Notas
1. **Confusión con Sellado**: Los desarrolladores a menudo confunden el propósito de `sealed` y `non-sealed`. Es importante recordar que `non-sealed` se utiliza para romper la restricción impuesta por una clase sellada, permitiendo una mayor flexibilidad en la jerarquía de clases.

2. **Uso Inadecuado**: No todas las subclases deben ser marcadas como `non-sealed`. Se recomienda usar este modificador únicamente cuando se desea que una clase específica pueda ser extensible, manteniendo otras subclases restringidas si es necesario.

3. **Compatibilidad**: `non-sealed` solo puede ser utilizado en subclases de clases selladas. Si se intenta aplicar a una clase que no es parte de una jerarquía sellada, el compilador generará un error.

## Resumen en Una Frase
El modificador `non-sealed` en Java permite extender clases selladas sin restricciones, brindando flexibilidad en la jerarquía de herencia.