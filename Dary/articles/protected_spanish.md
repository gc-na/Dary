<!--
Meta Description: # Modificador "protected" en Java: Entendiendo su Uso y Aplicaciones ## Sinopsis El modificador de acceso "protected" en Java permite que miembros (at...
Meta Keywords: protected, acceso, clase, public, java
-->

# Modificador "protected" en Java: Entendiendo su Uso y Aplicaciones

## Sinopsis
El modificador de acceso "protected" en Java permite que miembros (atributos y métodos) de una clase sean accesibles dentro de su propia clase, por clases del mismo paquete y por subclases, incluso si estas se encuentran en paquetes diferentes. Este modificador es fundamental para la herencia y la encapsulación en la programación orientada a objetos.

## Documentación
El modificador "protected" se utiliza en Java para controlar la visibilidad de los miembros de una clase. Su propósito principal es permitir que las subclases accedan a los miembros de una clase base, facilitando la extensión y modificación del comportamiento de las clases. 

### Uso
- **Declaración**: Se utiliza antes de la declaración de un atributo o método.
- **Acceso**: Los miembros declarados como "protected" pueden ser accedidos:
  - Desde la propia clase.
  - Desde cualquier clase en el mismo paquete.
  - Desde cualquier subclase, incluso si está en un paquete diferente.

### Ejemplo de Declaración
```java
public class ClaseBase {
    protected int numeroProtected;

    protected void metodoProtected() {
        System.out.println("Método protected llamado");
    }
}
```

## Ejemplos
### Ejemplo 1: Acceso desde la misma clase
```java
public class ClaseEjemplo {
    protected int valor;

    public void mostrarValor() {
        valor = 10;
        System.out.println("Valor: " + valor);
    }
}
```

### Ejemplo 2: Acceso desde el mismo paquete
```java
package miPaquete;

public class ClaseBase {
    protected void metodo() {
        System.out.println("Método de ClaseBase");
    }
}

public class ClaseDerivada extends ClaseBase {
    public void ejecutar() {
        metodo(); // Acceso permitido
    }
}
```

### Ejemplo 3: Acceso desde una subclase en otro paquete
```java
package otroPaquete;

import miPaquete.ClaseBase;

public class SubClase extends ClaseBase {
    public void ejecutar() {
        metodo(); // Acceso permitido
    }
}
```

## Explicación
Un error común es confundir el modificador "protected" con "private". Mientras que "private" limita el acceso solo a la propia clase, "protected" amplía el acceso a las subclases y a clases dentro del mismo paquete. Es importante recordar que el modificador "protected" no permite acceso desde clases que no son subclases, incluso si están en el mismo paquete.

### Consideraciones
- **No se puede usar en variables locales**: "protected" solo puede aplicarse a clases, métodos y atributos a nivel de instancia.
- **Herencia**: Al extender una clase, los miembros "protected" son accesibles, lo que fomenta la reutilización de código.
- **Visibilidad en Interfaces**: Los métodos en interfaces son implícitamente "public", y no pueden ser "protected".

## Resumen en Una Línea
El modificador "protected" en Java permite el acceso a miembros de clase desde la misma clase, clases del mismo paquete y subclases en paquetes diferentes, facilitando la herencia y la reutilización de código.