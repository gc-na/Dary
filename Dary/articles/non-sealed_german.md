<!--
Meta Description: # Non-Sealed in Java: Ein Leitfaden zur Verwendung und Bedeutung ## Synopsis Das Schlüsselwort „non-sealed“ in Java ermöglicht es Entwicklern, eine ni...
Meta Keywords: sealed, non, die, klasse, von
-->

# Non-Sealed in Java: Ein Leitfaden zur Verwendung und Bedeutung

## Synopsis
Das Schlüsselwort „non-sealed“ in Java ermöglicht es Entwicklern, eine nicht versiegelte Klasse oder ein nicht versiegeltes Interface zu deklarieren, um die Vererbung und Erweiterbarkeit in einer Hierarchie von Klassen zu steuern.

## Dokumentation
In Java 15 wurde das Konzept der Versiegelung (sealed classes) eingeführt, das es Entwicklern ermöglicht, den Zugriff auf die Vererbung zu kontrollieren. Mit dem Schlüsselwort „non-sealed“ können Entwickler eine Klasse oder ein Interface deklarieren, die von einer versiegelten Klasse abgeleitet sind, um die Einschränkungen der Vererbung aufzuheben.

Die Hauptziele von „non-sealed“ sind:
- **Erweiterbarkeit**: Erlaubt es anderen Klassen, von einer nicht versiegelten Klasse abzuleiten, selbst wenn sie von einer versiegelten Klasse stammt.
- **Flexibilität**: Ermöglicht es Entwicklern, mehr Freiheit zu haben, wenn es darum geht, wie sie ihre Klassenhierarchien gestalten und erweitern.

### Verwendung
Um eine Klasse oder ein Interface als „non-sealed“ zu deklarieren, verwenden Sie das Schlüsselwort „non-sealed“ vor der Deklaration der Klasse oder des Interfaces. Hier ist die allgemeine Syntax:

```java
non-sealed class Klassenname extends VersiegelteKlasse {
    // Implementierung
}
```

## Beispiele
Hier sind einige grundlegende Beispiele für die Verwendung von „non-sealed“ in Java:

### Beispiel 1: Nicht versiegelte Klasse
```java
sealed class Fahrzeug permits Auto, Motorrad {
    // Basisklasse für Fahrzeuge
}

non-sealed class Auto extends Fahrzeug {
    // Implementierung für Autos
}

class Motorrad extends Fahrzeug {
    // Implementierung für Motorräder
}

class Lkw extends Auto {
    // Lkw kann von Auto abgeleitet werden, da Auto non-sealed ist
}
```

### Beispiel 2: Nicht versiegeltes Interface
```java
sealed interface Tier permits Hund, Katze {
    void machenGeräusch();
}

non-sealed interface Haustier extends Tier {
    void spielen();
}

class Hund implements Haustier {
    public void machenGeräusch() {
        System.out.println("Wuff");
    }

    public void spielen() {
        System.out.println("Hund spielt");
    }
}
```

## Erklärung
Ein häufiges Missverständnis besteht darin, dass „non-sealed“ Klassen oder Interfaces keine Einschränkungen mehr haben. Das ist nicht korrekt. „Non-sealed“ hebt lediglich die Einschränkungen auf, die durch das „sealed“ Schlüsselwort einer übergeordneten Klasse oder eines Interfaces auferlegt wurden. Es ist wichtig zu beachten, dass „non-sealed“ nicht bedeutet, dass die Klasse oder das Interface von jeder beliebigen Klasse abgeleitet werden kann, sondern nur, dass die spezifischen Einschränkungen der übergeordneten versiegelten Klasse nicht mehr gelten.

Ein weiterer Punkt, den Entwickler beachten sollten, ist die Lesbarkeit des Codes. Das Übermaß an Vererbung und die Verwendung von „non-sealed“ kann zu komplexen und schwer verständlichen Klassenhierarchien führen. Es wird empfohlen, die Verwendung von „non-sealed“ sorgfältig zu planen und zu dokumentieren.

## Ein-Satz-Zusammenfassung
Das Schlüsselwort „non-sealed“ in Java ermöglicht es Entwicklern, Klassen und Interfaces zu erstellen, die von versiegelten Typen abgeleitet sind und die Einschränkungen der Vererbung aufheben.