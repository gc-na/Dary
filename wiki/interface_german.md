<!--
Meta Description: # Java-Interface: Grundlagen und Anwendung in der Programmierung ## Synopsis Ein Interface in Java ist ein Referenztyp, der eine Sammlung von abstrakt...
Meta Keywords: public, interface, die, void, java
-->

# Java-Interface: Grundlagen und Anwendung in der Programmierung

## Synopsis
Ein Interface in Java ist ein Referenztyp, der eine Sammlung von abstrakten Methoden definiert. Es ermöglicht die Implementierung von Mehrfachvererbung und fördert die Trennung von Implementierung und Schnittstelle.

## Dokumentation
Ein Interface in Java wird mit dem Schlüsselwort `interface` deklariert. Es ermöglicht Klassen, die von diesem Interface implementiert werden, die festgelegten Methoden zu verwenden, ohne die eigentliche Implementierung der Methoden bereitzustellen. Interfaces sind wichtig für die Definition von Verträgen, die eine Klasse erfüllen muss, und fördern die Flexibilität und Wiederverwendbarkeit des Codes.

### Zweck
- **Abstraktion**: Interfaces ermöglichen es, die Implementierungsdetails von der Schnittstelle zu trennen.
- **Multiple Inheritance**: Java unterstützt keine Mehrfachvererbung von Klassen, aber Interfaces erlauben es, mehrere Interfaces in einer Klasse zu implementieren.
- **Polymorphismus**: Durch Interfaces kann eine Variable des Interface-Typs unterschiedliche Objektarten zur Laufzeit annehmen.

### Verwendung
Ein Interface wird wie folgt deklariert:

```java
public interface MeinInterface {
    void meineMethode();
}
```

Eine Klasse, die dieses Interface implementiert, muss die Methode definieren:

```java
public class MeineKlasse implements MeinInterface {
    @Override
    public void meineMethode() {
        System.out.println("Methode implementiert!");
    }
}
```

## Beispiele
### Einfaches Beispiel
```java
public interface Tier {
    void machenGeräusch();
}

public class Hund implements Tier {
    @Override
    public void machenGeräusch() {
        System.out.println("Wuff!");
    }
}

public class Katze implements Tier {
    @Override
    public void machenGeräusch() {
        System.out.println("Miau!");
    }
}

public class Haupt {
    public static void main(String[] args) {
        Tier meinHund = new Hund();
        meinHund.machenGeräusch(); // Ausgabe: Wuff!

        Tier meineKatze = new Katze();
        meineKatze.machenGeräusch(); // Ausgabe: Miau!
    }
}
```

### Beispiel mit mehreren Interfaces
```java
public interface Schwimmen {
    void schwimmen();
}

public interface Fliegen {
    void fliegen();
}

public class Ente implements Schwimmen, Fliegen {
    @Override
    public void schwimmen() {
        System.out.println("Die Ente schwimmt.");
    }

    @Override
    public void fliegen() {
        System.out.println("Die Ente fliegt.");
    }
}
```

## Erklärung
Ein häufiges Problem beim Arbeiten mit Interfaces ist, dass Entwickler dazu neigen, Interfaces mit einer Vielzahl von Methoden zu überladen, was die Implementierung erschwert. Es ist ratsam, Interfaces klein und fokussiert zu halten, um die Einhaltung des Interface Segregation Principles zu gewährleisten.

Zusätzlich ist zu beachten, dass alle Methoden in einem Interface standardmäßig `public` und `abstract` sind. Ab Java 8 können Interfaces auch Standardmethoden (`default`) und statische Methoden enthalten. 

```java
public interface Fahrzeug {
    void fahren();
    
    default void tanken() {
        System.out.println("Das Fahrzeug tankt.");
    }
}
```

## Ein-Satz-Zusammenfassung
Ein Interface in Java definiert einen Vertrag für Klassen, um Methoden zu implementieren, fördert die Abstraktion und ermöglicht Mehrfachvererbung.