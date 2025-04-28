<!--
Meta Description: # Abstract in Java: Verständnis und Anwendung ## Synopsis Das Schlüsselwort "abstract" in Java wird verwendet, um abstrakte Klassen und Methoden zu de...
Meta Keywords: abstrakte, methoden, die, klassen, nicht
-->

# Abstract in Java: Verständnis und Anwendung

## Synopsis
Das Schlüsselwort "abstract" in Java wird verwendet, um abstrakte Klassen und Methoden zu definieren. Es ermöglicht die Erstellung von Basisklassen, die nicht instanziiert werden können, sondern als Vorlage für abgeleitete Klassen dienen.

## Dokumentation
In Java bezeichnet das Schlüsselwort "abstract" eine Klasse oder Methode, die nicht vollständig implementiert ist. Abstrakte Klassen können abstrakte Methoden enthalten, die von den abgeleiteten Klassen implementiert werden müssen. 

### Zweck
Der Hauptzweck von abstrakten Klassen ist die Bereitstellung einer gemeinsamen Schnittstelle für eine Gruppe von verwandten Klassen. Sie ermöglichen die Definition von Methoden, die in den Unterklassen konkretisiert werden müssen, und fördern die Wiederverwendbarkeit und Organisation des Codes.

### Verwendung
- **Abstrakte Klassen**: Eine Klasse, die als abstrakt deklariert ist, kann nicht instanziiert werden. Sie kann sowohl abstrakte als auch nicht-abstrakte Methoden enthalten.
- **Abstrakte Methoden**: Diese Methoden haben keine Implementierung in der abstrakten Klasse und müssen in den Unterklassen überschrieben werden.

### Syntax
```java
abstract class Klassenname {
    abstract void abstrakteMethode();
    
    void normaleMethode() {
        // Implementierung
    }
}
```

## Beispiele
### Beispiel 1: Abstrakte Klasse und Methode
```java
abstract class Fahrzeug {
    abstract void fahren(); // Abstrakte Methode

    void info() {
        System.out.println("Dies ist ein Fahrzeug.");
    }
}

class Auto extends Fahrzeug {
    void fahren() {
        System.out.println("Das Auto fährt.");
    }
}

public class Main {
    public static void main(String[] args) {
        Fahrzeug meinAuto = new Auto();
        meinAuto.fahren(); // Ausgabe: Das Auto fährt.
        meinAuto.info();   // Ausgabe: Dies ist ein Fahrzeug.
    }
}
```

### Beispiel 2: Mehrere Unterklassen
```java
abstract class Tier {
    abstract void geräuschMachen();
}

class Hund extends Tier {
    void geräuschMachen() {
        System.out.println("Wuff!");
    }
}

class Katze extends Tier {
    void geräuschMachen() {
        System.out.println("Miau!");
    }
}

public class Main {
    public static void main(String[] args) {
        Tier meinHund = new Hund();
        Tier meineKatze = new Katze();
        
        meinHund.geräuschMachen(); // Ausgabe: Wuff!
        meineKatze.geräuschMachen(); // Ausgabe: Miau!
    }
}
```

## Erklärung
Ein häufiges Missverständnis bei der Verwendung von abstrakten Klassen ist, dass sie nicht instanziiert werden können. Es ist wichtig zu beachten, dass, obwohl die abstrakte Klasse selbst nicht instanziiert werden kann, ihre Unterklassen instanziiert werden können, solange sie alle abstrakten Methoden implementieren.

Ein weiterer Punkt ist, dass eine Klasse sowohl abstrakt als auch konkret sein kann. Man kann eine Methode als abstrakt deklarieren und gleichzeitig nicht-abstrakte Methoden implementieren.

### Fallstricke
- **Nicht implementierte abstrakte Methoden**: Wenn eine abgeleitete Klasse nicht alle abstrakten Methoden implementiert, wird sie ebenfalls zu einer abstrakten Klasse, was die Instanziierung weiter einschränkt.
- **Abstrakte Klassen können keine finalen Methoden haben**: Da finale Methoden nicht überschrieben werden können, macht es keinen Sinn, sie in einer abstrakten Klasse zu definieren.

## Einzeiliger Überblick
Das Schlüsselwort "abstract" in Java definiert Klassen und Methoden, die nicht vollständig implementiert sind und somit als Vorlage für abgeleitete Klassen dienen.