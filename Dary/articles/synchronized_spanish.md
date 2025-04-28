<!--
Meta Description: # Synchronized en Java: Sincronización de Hilos en Programación Concurrente ## Sinopsis El modificador `synchronized` en Java es una herramienta clave...
Meta Keywords: synchronized, que, java, public, hilo
-->

# Synchronized en Java: Sincronización de Hilos en Programación Concurrente

## Sinopsis
El modificador `synchronized` en Java es una herramienta clave para la programación concurrente, ya que permite controlar el acceso a un recurso compartido, evitando condiciones de carrera y garantizando la integridad de los datos en entornos multihilo.

## Documentación
### Propósito
El propósito del modificador `synchronized` es asegurar que solo un hilo pueda acceder a un bloque de código o método específico al mismo tiempo. Esto es esencial en aplicaciones donde varios hilos pueden intentar modificar un recurso compartido simultáneamente.

### Uso
El modificador `synchronized` puede ser utilizado de dos maneras:

1. **Métodos sincronizados**: Se aplica a métodos completos, bloqueando el acceso al método para otros hilos hasta que finalice su ejecución.
   ```java
   public synchronized void metodoSincronizado() {
       // Código que manipula recursos compartidos.
   }
   ```

2. **Bloques sincronizados**: Se aplica a bloques de código dentro de un método, permitiendo un control más granular sobre qué parte del código debe ser sincronizada.
   ```java
   public void metodo() {
       synchronized (this) {
           // Código que manipula recursos compartidos.
       }
   }
   ```

### Detalles
- **Bloqueo de objetos**: Cuando un hilo ejecuta un método sincronizado o un bloque sincronizado, se adquiere un bloqueo en el objeto al que pertenece. Si otro hilo intenta ejecutar un método sincronizado en el mismo objeto, se detendrá hasta que el primer hilo libere el bloqueo.
- **Bloqueo de clases**: También es posible sincronizar métodos estáticos, lo que implica un bloqueo en la clase misma.
   ```java
   public static synchronized void metodoEstatico() {
       // Código sincronizado.
   }
   ```

## Ejemplos
### Ejemplo de Método Sincronizado
```java
public class Contador {
    private int cuenta = 0;

    public synchronized void incrementar() {
        cuenta++;
    }

    public synchronized int obtenerCuenta() {
        return cuenta;
    }
}
```

### Ejemplo de Bloque Sincronizado
```java
public class RecursoCompartido {
    private int dato;

    public void actualizarDato(int nuevoDato) {
        synchronized (this) {
            dato = nuevoDato;
        }
    }
}
```

## Explicación
### Errores Comunes
- **Bloqueo Innecesario**: Sincronizar métodos o bloques que no acceden a recursos compartidos puede disminuir el rendimiento sin proporcionar beneficios de seguridad.
- **Deadlocks**: Si varios hilos intentan acceder a múltiples recursos en diferentes órdenes, pueden quedar bloqueados indefinidamente.
- **Visibilidad de Cambios**: Sin `synchronized`, un hilo puede no ver los cambios realizados por otro hilo debido a caching de CPU; `synchronized` garantiza la visibilidad adecuada.

### Notas Adicionales
- `synchronized` es una forma de exclusión mutua, pero existen mecanismos más avanzados como `ReentrantLock` que ofrecen flexibilidad adicional.
- Usar `volatile` junto con `synchronized` puede mejorar la visibilidad de variables, aunque no sustituye la necesidad de sincronización.

## Resumen en Una Línea
El modificador `synchronized` en Java es fundamental para gestionar el acceso concurrente a recursos compartidos, evitando condiciones de carrera y garantizando la integridad de los datos.