<!--
Meta Description: # Der "case"-Befehl in Java: Verwendung und Beispiele ## Synopsis Der `case`-Befehl in Java ist Teil der `switch`-Anweisung, die eine Mehrfachverzweig...
Meta Keywords: case, der, break, die, system
-->

# Der "case"-Befehl in Java: Verwendung und Beispiele

## Synopsis
Der `case`-Befehl in Java ist Teil der `switch`-Anweisung, die eine Mehrfachverzweigung ermöglicht. Er wird verwendet, um verschiedene Ausführungswege basierend auf dem Wert einer Variablen zu bestimmen.

## Dokumentation
Der `case`-Befehl wird in Verbindung mit der `switch`-Anweisung verwendet, um verschiedene Codeblöcke auszuführen, die einer bestimmten Bedingung entsprechen. Die Syntax sieht folgendermaßen aus:

```java
switch (variable) {
    case wert1:
        // Codeblock für wert1
        break;
    case wert2:
        // Codeblock für wert2
        break;
    default:
        // Codeblock für alle anderen Werte
}
```

### Zweck
Der Hauptzweck der `switch`-Anweisung und der damit verbundenen `case`-Befehle ist es, die Lesbarkeit und Wartbarkeit des Codes zu verbessern, insbesondere wenn mehrere Bedingungen überprüft werden müssen.

### Verwendung
- **Variable**: Die Variable, die überprüft wird, kann vom Typ `int`, `char`, `String` oder `enum` sein.
- **Werte**: Jeder `case`-Wert muss eine Konstante sein, die im Bereich des Typs der Variablen liegt.
- **Break-Anweisung**: Die `break`-Anweisung wird verwendet, um die Ausführung aus der `switch`-Anweisung zu beenden. Ohne `break` wird der Code in den nachfolgenden `case`-Blöcken fortgesetzt (auch bekannt als "fall-through").

## Beispiele
Hier sind einige einfache Beispiele zur Veranschaulichung der Verwendung des `case`-Befehls in Java:

### Beispiel 1: Ganzzahlige Werte

```java
int tag = 3;

switch (tag) {
    case 1:
        System.out.println("Montag");
        break;
    case 2:
        System.out.println("Dienstag");
        break;
    case 3:
        System.out.println("Mittwoch");
        break;
    default:
        System.out.println("Invalider Tag");
}
```

### Beispiel 2: Zeichenwerte

```java
char note = 'B';

switch (note) {
    case 'A':
        System.out.println("Ausgezeichnet!");
        break;
    case 'B':
        System.out.println("Gut gemacht!");
        break;
    case 'C':
        System.out.println("Befriedigend.");
        break;
    default:
        System.out.println("Note nicht erkannt.");
}
```

### Beispiel 3: String-Werte

```java
String farbe = "Rot";

switch (farbe) {
    case "Rot":
        System.out.println("Die Farbe ist Rot.");
        break;
    case "Blau":
        System.out.println("Die Farbe ist Blau.");
        break;
    default:
        System.out.println("Farbe nicht erkannt.");
}
```

## Erklärung
Ein häufiges Problem beim Arbeiten mit `case`-Befehlen ist das Vergessen der `break`-Anweisung, was zu unerwartetem Verhalten führen kann, da der Code in die nachfolgenden `case`-Blöcke fortgesetzt wird. Zudem ist es wichtig, sicherzustellen, dass die `case`-Werte konstant sind und vom Typ der übergebenen Variable übereinstimmen. Bei der Verwendung von `String`-Werten ist ebenfalls darauf zu achten, dass der Vergleich case-sensitive ist (Groß-/Kleinschreibung beachten).

## Ein-Satz-Zusammenfassung
Der `case`-Befehl in Java ermöglicht eine strukturierte und lesbare Handhabung von Mehrfachverzweigungen innerhalb der `switch`-Anweisung.