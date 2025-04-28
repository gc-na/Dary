<!--
Meta Description: # Sealed Classes in Java: Eine Einführung und Anwendung ## Synopsis Sealed Classes in Java ermöglichen es Entwicklern, die Vererbungshierarchie ihrer ...
Meta Keywords: sealed, java, public, class, klassen
-->

# Sealed Classes in Java: Eine Einführung und Anwendung

## Synopsis
Sealed Classes in Java ermöglichen es Entwicklern, die Vererbungshierarchie ihrer Klassen zu kontrollieren, indem sie einschränken, welche Klassen von ihnen abgeleitet werden können.

## Documentation
Sealed Classes wurden mit Java 15 als Vorschau eingeführt und sind ab Java 17 ein fester Bestandteil der Sprache. Ihr Hauptzweck besteht darin, eine klar definierte Hierarchie von Klassen zu schaffen, die die Erweiterbarkeit der Anwendung besser steuern kann. Dies ist besonders nützlich, um sicherzustellen, dass nur eine bestimmte Gruppe von Klassen die Funktionalität einer Basisklasse erweitern kann.

Ein `sealed` Schlüsselwort wird verwendet, um eine Klasse als versiegelt zu kennzeichnen. Die abgeleiteten Klassen müssen dann mit den Schlüsselwörtern `permits` aufgeführt werden. Diese Klassen können entweder `final`, `sealed` oder `non-sealed` sein.

### Beispiel:
```java
public sealed class Fahrzeug permits Auto, Motorrad {
    // Klasseninhalt
}

public final class Auto extends Fahrzeug {
    // Implementierung für Auto
}

public non-sealed class Motorrad extends Fahrzeug {
    // Implementierung für Motorrad
}
```

In diesem Beispiel ist `Fahrzeug` eine versiegelte Klasse, die nur `Auto` und `Motorrad` als ihre Unterklassen erlaubt.

## Examples
Hier sind einige grundlegende Beispiele zur Verwendung von sealed classes in Java:

### Beispiel 1: Einfache versiegelte Klasse
```java
public sealed class Tier permits Hund, Katze {
    // Basisklasse
}

public final class Hund extends Tier {
    // Hunde spezifische Implementierung
}

public final class Katze extends Tier {
    // Katzen spezifische Implementierung
}
```

### Beispiel 2: Versiegelte Klasse mit non-sealed
```java
public sealed class Fahrzeug permits Auto, Motorrad {
    // Basisklasse
}

public non-sealed class Auto extends Fahrzeug {
    // Auto spezifische Implementierung
}

public final class Motorrad extends Fahrzeug {
    // Motorrad spezifische Implementierung
}
```

## Explanation
Ein häufiger Stolperstein bei der Verwendung von sealed classes ist, dass alle Unterklassen einer versiegelten Klasse ebenfalls entweder `final`, `sealed` oder `non-sealed` sein müssen. Wenn eine Klasse nicht als eines dieser Typen deklariert wird, führt dies zu einem Kompilierungsfehler.

Ein weiterer Punkt ist, dass versiegelte Klassen die Flexibilität der Vererbung einschränken können. Daher sollte man sorgfältig abwägen, wo und wie man sie anwendet.

## One Line Summary
Sealed Classes in Java bieten eine kontrollierte Vererbung, indem sie einschränken, welche Klassen von einer versiegelten Klasse abgeleitet werden können.