<!--
Meta Description: # Verwendung von "super" in Java: Schlüsselwort für die Vererbung ## Synopsis Das Schlüsselwort "super" in Java wird verwendet, um auf die Mitglieder ...
Meta Keywords: der, super, kind, methode, klasse
-->

# Verwendung von "super" in Java: Schlüsselwort für die Vererbung

## Synopsis
Das Schlüsselwort "super" in Java wird verwendet, um auf die Mitglieder der übergeordneten Klasse zuzugreifen. Es spielt eine zentrale Rolle in der Vererbung, indem es Entwicklern ermöglicht, Konstruktoren, Methoden und Variablen der Elternklasse zu referenzieren.

## Dokumentation
### Zweck
In Java ermöglicht das Schlüsselwort "super" den Zugriff auf die Methoden und Variablen der übergeordneten Klasse. Es ist besonders nützlich im Kontext der Vererbung, wenn eine abgeleitete Klasse Methoden oder Variablen mit denselben Namen wie in der übergeordneten Klasse hat. Mit "super" kann der Programmierer klarstellen, welche Version einer Methode oder Variable er verwenden möchte.

### Verwendung
Das Schlüsselwort "super" kann in verschiedenen Kontexten verwendet werden:
1. **Zugriff auf übergeordnete Methoden**: Wenn eine Methode in der abgeleiteten Klasse die gleiche Signatur wie eine Methode in der übergeordneten Klasse hat, kann "super" verwendet werden, um die übergeordnete Methode aufzurufen.
2. **Zugriff auf übergeordnete Variablen**: In Fällen, in denen eine abgeleitete Klasse eine Variable mit dem gleichen Namen wie eine in der übergeordneten Klasse hat, wird "super" verwendet, um auf die Variable der Elternklasse zuzugreifen.
3. **Konstruktoraufruf**: Im Konstruktor einer abgeleiteten Klasse kann "super()" verwendet werden, um den Konstruktor der übergeordneten Klasse aufzurufen.

### Details
- "super" muss immer innerhalb einer Methode oder eines Konstruktors verwendet werden und kann nicht statisch sein.
- Wenn der Konstruktor der übergeordneten Klasse Parameter hat, können diese beim Aufruf von "super" übergeben werden.
- "super" kann nicht in statischen Kontexten verwendet werden, da es sich auf Instanzen bezieht.

## Beispiele
### Beispiel 1: Zugriff auf übergeordnete Methoden
```java
class Eltern {
    void methode() {
        System.out.println("Methode in Elternklasse");
    }
}

class Kind extends Eltern {
    void methode() {
        super.methode(); // Aufruf der Methode in der Elternklasse
        System.out.println("Methode in Kindklasse");
    }
}

public class Main {
    public static void main(String[] args) {
        Kind kind = new Kind();
        kind.methode();
    }
}
```
**Ausgabe:**
```
Methode in Elternklasse
Methode in Kindklasse
```

### Beispiel 2: Zugriff auf übergeordnete Variablen
```java
class Eltern {
    String name = "Eltern";
}

class Kind extends Eltern {
    String name = "Kind";

    void printNames() {
        System.out.println("Name in Kindklasse: " + name);
        System.out.println("Name in Elternklasse: " + super.name);
    }
}

public class Main {
    public static void main(String[] args) {
        Kind kind = new Kind();
        kind.printNames();
    }
}
```
**Ausgabe:**
```
Name in Kindklasse: Kind
Name in Elternklasse: Eltern
```

### Beispiel 3: Konstruktoraufruf
```java
class Eltern {
    Eltern() {
        System.out.println("Konstruktor der Elternklasse");
    }
}

class Kind extends Eltern {
    Kind() {
        super(); // Aufruf des Konstruktors der Elternklasse
        System.out.println("Konstruktor der Kindklasse");
    }
}

public class Main {
    public static void main(String[] args) {
        Kind kind = new Kind();
    }
}
```
**Ausgabe:**
```
Konstruktor der Elternklasse
Konstruktor der Kindklasse
```

## Erklärung
Ein häufiges Missverständnis ist die Annahme, dass "super" auch in statischen Kontexten verwendet werden kann. "super" ist nur für Instanzmethoden und -variablen gültig. Ein weiterer häufiger Fehler ist die falsche Verwendung von "super()" im Konstruktor, ohne die korrekten Parameter zu übergeben, was zu Kompilierungsfehlern führen kann.

## Zusammenfassung in einem Satz
Das "super"-Schlüsselwort in Java ermöglicht den Zugriff auf Mitglieder der übergeordneten Klasse und ist entscheidend für die Implementierung von Vererbung.