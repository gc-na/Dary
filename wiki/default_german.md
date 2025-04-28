<!--
Meta Description: # Das Schlüsselwort "default" in Java: Eine umfassende Übersicht ## Synopsis Das Schlüsselwort "default" in Java wird verwendet, um Standardmethoden i...
Meta Keywords: die, ist, das, default, eine
-->

# Das Schlüsselwort "default" in Java: Eine umfassende Übersicht

## Synopsis
Das Schlüsselwort "default" in Java wird verwendet, um Standardmethoden in Schnittstellen zu definieren, die eine Implementierung enthalten. Es ermöglicht es Entwicklern, neue Methoden in bereits existierenden Schnittstellen hinzuzufügen, ohne bestehende Implementierungen zu brechen.

## Dokumentation
In Java, eingeführt mit Java 8, ermöglicht das Schlüsselwort "default" die Erstellung von Standardmethoden in Schnittstellen. Eine Standardmethode ist eine Methode, die eine Implementierung innerhalb der Schnittstelle selbst hat. Dies ist besonders nützlich, um die Rückwärtskompatibilität von Schnittstellen zu wahren, während gleichzeitig neue Funktionalitäten bereitgestellt werden.

### Zweck
Der Hauptzweck von "default" ist es, Entwicklern zu ermöglichen, Schnittstellen zu erweitern, ohne dass alle implementierenden Klassen aktualisiert werden müssen. Dies ist besonders wichtig in großen Codebasen, wo zahlreiche Klassen eine bestimmte Schnittstelle implementieren.

### Verwendung
Um eine Standardmethode zu definieren, fügen Sie das Schlüsselwort "default" gefolgt von der Implementierung der Methode in der Schnittstelle hinzu. Hier ist das grundlegende Format:

```java
public interface MeinInterface {
    default void meineStandardmethode() {
        System.out.println("Dies ist eine Standardmethode.");
    }
}
```

## Beispiele
Hier sind einige einfache Beispiele zur Veranschaulichung der Verwendung von "default":

### Beispiel 1: Einfache Standardmethode
```java
public interface Fahrzeug {
    default void starten() {
        System.out.println("Das Fahrzeug startet.");
    }
}

public class Auto implements Fahrzeug {
    // Auto hat Zugriff auf die Standardmethode starten
}

public class Main {
    public static void main(String[] args) {
        Fahrzeug meinAuto = new Auto();
        meinAuto.starten(); // Ausgabe: Das Fahrzeug startet.
    }
}
```

### Beispiel 2: Überschreiben einer Standardmethode
```java
public interface Gerät {
    default void einschalten() {
        System.out.println("Das Gerät ist eingeschaltet.");
    }
}

public class Fernseher implements Gerät {
    @Override
    public void einschalten() {
        System.out.println("Der Fernseher wird eingeschaltet.");
    }
}

public class Main {
    public static void main(String[] args) {
        Gerät meinFernseher = new Fernseher();
        meinFernseher.einschalten(); // Ausgabe: Der Fernseher wird eingeschaltet.
    }
}
```

## Erklärung
Ein häufiges Problem, das beim Arbeiten mit Standardmethoden auftreten kann, ist die Konfliktsituation, wenn eine Klasse mehrere Schnittstellen implementiert, die jeweils eine Standardmethode mit demselben Namen haben. In solchen Fällen muss die implementierende Klasse explizit die Methode überschreiben, um den Konflikt zu lösen.

Ein weiteres zu beachtendes Detail ist, dass Standardmethoden nicht statisch sein können und nicht in einer abstrakten Klasse definiert werden können. Sie sind ausschließlich für Schnittstellen reserviert. 

Zusätzlich ist zu beachten, dass die Verwendung von Standardmethoden in Schnittstellen den Code flexibler und wartungsfreundlicher machen kann, aber auch zu Verwirrung führen kann, wenn nicht klar ist, welche Implementierung verwendet wird.

## Ein-Satz-Zusammenfassung
Das Schlüsselwort "default" in Java ermöglicht die Definition von Standardmethoden in Schnittstellen, wodurch die Rückwärtskompatibilität und die Erweiterbarkeit von bestehenden Schnittstellen gewährleistet werden.