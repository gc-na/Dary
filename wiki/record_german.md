<!--
Meta Description: # Java Record: Die neue Datenklasse für effiziente Datenhaltung ## Synopsis In Java 14 eingeführt als Preview-Feature und ab Java 16 stabilisiert, erm...
Meta Keywords: die, records, java, person, record
-->

# Java Record: Die neue Datenklasse für effiziente Datenhaltung

## Synopsis
In Java 14 eingeführt als Preview-Feature und ab Java 16 stabilisiert, ermöglichen Records eine einfache und prägnante Möglichkeit, Datenklassen zu erstellen, die unveränderlich sind und automatisch grundlegende Methoden wie `equals()`, `hashCode()` und `toString()` generieren.

## Documentation
Records sind eine spezielle Art von Klassen in Java, die hauptsächlich dazu dienen, Daten zu halten. Sie bieten eine reduzierte Syntax, um die Boilerplate-Codierung zu minimieren und die Lesbarkeit zu erhöhen. Ein Record besteht aus einer festen Anzahl von Feldern (auch als Komponenten bezeichnet), die beim Erstellen des Records definiert werden. Die Hauptmerkmale von Records sind:

- **Unveränderlichkeit**: Die Felder eines Records sind final, was bedeutet, dass sie nach der Initialisierung nicht mehr geändert werden können.
- **Automatische Methoden**: Der Compiler generiert automatisch die Methoden `equals()`, `hashCode()`, und `toString()`, die auf den Feldern des Records basieren.
- **Kompakte Syntax**: Die Definition eines Records ist kürzer als die einer regulären Klasse.

### Definition eines Records
Ein Record wird mit dem Schlüsselwort `record` definiert, gefolgt vom Namen und den Parametern in Klammern. Hier ein einfaches Beispiel:

```java
record Person(String name, int alter) {}
```

## Examples
Hier sind einige grundlegende Beispiele zur Verwendung von Records:

### Beispiel 1: Erstellung und Nutzung eines Records

```java
record Person(String name, int alter) {}

public class Main {
    public static void main(String[] args) {
        Person person = new Person("Max Mustermann", 30);
        System.out.println(person.name()); // Ausgabe: Max Mustermann
        System.out.println(person.alter()); // Ausgabe: 30
        System.out.println(person); // Ausgabe: Person[name=Max Mustermann, alter=30]
    }
}
```

### Beispiel 2: Nutzung von Records in einer Liste

```java
import java.util.List;

record Produkt(String name, double preis) {}

public class Main {
    public static void main(String[] args) {
        List<Produkt> produkte = List.of(new Produkt("Tisch", 199.99), new Produkt("Stuhl", 89.99));

        for (Produkt p : produkte) {
            System.out.println(p.name() + ": " + p.preis());
        }
    }
}
```

## Explanation
Einige häufige Fallstricke und zusätzliche Hinweise zu Records in Java:

- **Vererbung**: Records können nicht von anderen Klassen erben, da sie automatisch die `final`-Eigenschaft besitzen. Sie können jedoch Interfaces implementieren.
- **Konstruktoren**: Records können auch benutzerdefinierte Konstruktoren haben, solange sie die gleichen Parameter wie die Komponenten der Record-Klasse verwenden.
  
  ```java
  record Person(String name, int alter) {
      public Person {
          if (alter < 0) {
              throw new IllegalArgumentException("Alter kann nicht negativ sein.");
          }
      }
  }
  ```

- **Kein Setter**: Da die Felder final sind, gibt es keine Setter-Methoden in Records, was ihre Unveränderlichkeit unterstützt.

## One Line Summary
Records in Java bieten eine kompakte, unveränderliche Möglichkeit zur Definition von Datenklassen mit automatischer Generierung wichtiger Methoden.