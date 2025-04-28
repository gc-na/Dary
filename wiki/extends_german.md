<!--
Meta Description: # Vererbung in Java: Die Verwendung von "extends" ## Synopsis In der Programmiersprache Java ermöglicht das Schlüsselwort „extends“ die Erstellung von...
Meta Keywords: der, die, oberklasse, java, klasse
-->

# Vererbung in Java: Die Verwendung von "extends"

## Synopsis
In der Programmiersprache Java ermöglicht das Schlüsselwort „extends“ die Erstellung von Unterklassen, die von einer übergeordneten Klasse erben. Dies fördert die Wiederverwendbarkeit von Code und erleichtert die Implementierung objektorientierter Prinzipien.

## Dokumentation
### Zweck
Das Schlüsselwort „extends“ wird in Java verwendet, um eine neue Klasse zu definieren, die von einer bestehenden Klasse erbt. Die neue Klasse, auch bekannt als Unterklasse oder abgeleitete Klasse, erhält die Eigenschaften und Methoden der übergeordneten Klasse (auch Basisklasse oder Elternklasse genannt).

### Verwendung
Um eine Klasse als Unterklasse zu definieren, wird die Syntax `class Unterklasse extends Oberklasse` verwendet. Dies ermöglicht der Unterklasse den Zugriff auf öffentliche und geschützte Mitglieder der Oberklasse.

#### Syntax
```java
class Oberklasse {
    // Eigenschaften und Methoden der Oberklasse
}

class Unterklasse extends Oberklasse {
    // Eigenschaften und Methoden der Unterklasse
}
```

### Details
- **Einzelvererbung**: Java unterstützt nur die Einzelvererbung, d.h. eine Klasse kann nur von einer einzigen anderen Klasse erben.
- **Methodenüberschreibung**: Unterklassen können Methoden der Oberklasse überschreiben, um spezifisches Verhalten zu implementieren.
- **Konstruktoren**: Konstruktoren der Oberklasse werden nicht vererbt, aber die Unterklasse kann den Konstruktor der Oberklasse mit `super()` aufrufen.
- **Polymorphismus**: Das Konzept der Vererbung unterstützt auch Polymorphismus, wodurch Objekte der Unterklasse als Objekte der Oberklasse behandelt werden können.

## Beispiele
### Einfaches Beispiel
```java
class Tier {
    void essen() {
        System.out.println("Das Tier isst.");
    }
}

class Hund extends Tier {
    void bellen() {
        System.out.println("Der Hund bellt.");
    }
}

public class Test {
    public static void main(String[] args) {
        Hund meinHund = new Hund();
        meinHund.essen(); // Ausgabe: Das Tier isst.
        meinHund.bellen(); // Ausgabe: Der Hund bellt.
    }
}
```

### Methodenüberschreibung
```java
class Fahrzeug {
    void fahren() {
        System.out.println("Das Fahrzeug fährt.");
    }
}

class Auto extends Fahrzeug {
    @Override
    void fahren() {
        System.out.println("Das Auto fährt.");
    }
}

public class Test {
    public static void main(String[] args) {
        Fahrzeug meinFahrzeug = new Auto();
        meinFahrzeug.fahren(); // Ausgabe: Das Auto fährt.
    }
}
```

## Erklärung
### Häufige Fallstricke
- **Zugriffsmodifizierer**: Wenn Sie versuchen, auf private Mitglieder der Oberklasse in der Unterklasse zuzugreifen, wird ein Kompilierungsfehler angezeigt. Private Mitglieder sind nicht vererbbar.
- **Mehrfachvererbung**: Java unterstützt keine Mehrfachvererbung durch Klassen. Dies kann zu Verwirrung führen, wenn Entwickler versuchen, mehrere Klassen zu erben. Stattdessen kann Java Schnittstellen verwenden, um ähnliche Funktionalitäten zu erreichen.
- **Konstruktoraufrufe**: Vergessen Sie nicht, den Konstruktor der Oberklasse im Konstruktor der Unterklasse aufzurufen, wenn Sie spezifische Initialisierungen benötigen. Andernfalls wird der Standardkonstruktor aufgerufen.

## Zusammenfassung in einer Zeile
Das Schlüsselwort „extends“ in Java ermöglicht es einer Klasse, von einer anderen zu erben, wodurch die Wiederverwendbarkeit von Code und die Implementierung von objektorientierten Prinzipien gefördert werden.