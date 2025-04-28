<!--
Meta Description: # Der "new"-Operator in Java: Erstellung von Objekten ## Synopsis Der `new`-Operator in Java ist ein grundlegendes Schlüsselwort, das verwendet wird, ...
Meta Keywords: new, der, java, operator, ein
-->

# Der "new"-Operator in Java: Erstellung von Objekten

## Synopsis
Der `new`-Operator in Java ist ein grundlegendes Schlüsselwort, das verwendet wird, um neue Objekte zu instanziieren. Es spielt eine entscheidende Rolle in der objektorientierten Programmierung und ist unerlässlich für die Erstellung von Instanzen von Klassen.

## Dokumentation
Der `new`-Operator wird in Java verwendet, um Speicherplatz für ein neues Objekt zu reservieren und dessen Konstruktor aufzurufen. Wenn Sie eine Klasse definieren, können Sie mit `new` eine Instanz dieser Klasse erstellen, wodurch Sie auf ihre Methoden und Attribute zugreifen können.

### Verwendung
Die allgemeine Syntax zur Verwendung des `new`-Operators lautet:

```java
KlasseName objektName = new KlasseName();
```

### Details
- **Speicherzuweisung:** Der `new`-Operator weist zur Laufzeit Speicher für das Objekt zu.
- **Konstruktoraufruf:** Nach der Speichzuweisung wird der Konstruktor der Klasse aufgerufen, um das Objekt zu initialisieren.
- **Referenz:** Der `new`-Operator gibt eine Referenz auf das neu erstellte Objekt zurück, die in einer Variablen gespeichert werden kann.

## Beispiele
Hier sind einige grundlegende Beispiele zur Verwendung des `new`-Operators in Java:

### Beispiel 1: Erstellen eines Objekts einer Klasse

```java
class Auto {
    String marke;

    Auto(String marke) {
        this.marke = marke;
    }
}

public class Main {
    public static void main(String[] args) {
        Auto meinAuto = new Auto("Volkswagen");
        System.out.println("Marke: " + meinAuto.marke);
    }
}
```

### Beispiel 2: Erstellen mehrerer Objekte

```java
class Hund {
    String name;

    Hund(String name) {
        this.name = name;
    }
}

public class Main {
    public static void main(String[] args) {
        Hund hund1 = new Hund("Bello");
        Hund hund2 = new Hund("Max");
        System.out.println(hund1.name + " und " + hund2.name + " spielen.");
    }
}
```

## Erklärung
Ein häufiger Fallstrick bei der Verwendung des `new`-Operators in Java ist die Verwirrung über den Unterschied zwischen Referenzen und Objekten. Wenn Sie ein Objekt mit dem `new`-Operator erstellen, speichern Sie die Referenz auf das Objekt, nicht das Objekt selbst. Dies führt zu Missverständnissen, insbesondere bei der Zuweisung und dem Vergleich von Objekten.

Ein weiterer Punkt, den es zu beachten gilt, ist der Aufruf von Konstruktoren. Wenn ein Konstruktor Parameter benötigt, müssen Sie sicherstellen, dass Sie die richtigen Argumente übergeben. Andernfalls wird ein Kompilierungsfehler verursacht.

## Einzeiler Zusammenfassung
Der `new`-Operator in Java ist entscheidend für die Instanziierung von Objekten und den Aufruf ihrer Konstruktoren.