<!--
Meta Description: # "do"-Schleife in Java: Verwendung und Beispiele ## Synopsis Die "do"-Schleife in Java ermöglicht die wiederholte Ausführung eines Codeblocks, solang...
Meta Keywords: die, schleife, der, wird, bedingung
-->

# "do"-Schleife in Java: Verwendung und Beispiele

## Synopsis
Die "do"-Schleife in Java ermöglicht die wiederholte Ausführung eines Codeblocks, solange eine bestimmte Bedingung erfüllt ist. Sie unterscheidet sich von der "while"-Schleife, indem die Bedingung am Ende der Schleife überprüft wird, was sicherstellt, dass der Codeblock mindestens einmal ausgeführt wird.

## Dokumentation
Die "do"-Schleife hat die folgende Syntax:

```java
do {
    // Codeblock
} while (Bedingung);
```

### Zweck
Die "do"-Schleife wird verwendet, um einen bestimmten Codeblock mindestens einmal auszuführen, bevor die Bedingung überprüft wird. Dies ist nützlich in Szenarien, in denen der Code innerhalb der Schleife mindestens einmal ausgeführt werden muss, beispielsweise bei der Benutzereingabe.

### Verwendung
Um eine "do"-Schleife zu verwenden, müssen Sie:
1. Den Codeblock definieren, der wiederholt werden soll.
2. Die Bedingung angeben, die das Fortsetzen oder Beenden der Schleife bestimmt.

### Details
- Der Code innerhalb der "do"-Schleife wird ausgeführt, bevor die Bedingung überprüft wird.
- Wenn die Bedingung "true" ist, wird die Schleife erneut durchlaufen.
- Wenn die Bedingung "false" ist, wird die Schleife beendet.

## Beispiele
### Beispiel 1: Grundlegende do-Schleife
```java
int i = 0;
do {
    System.out.println("Zähler: " + i);
    i++;
} while (i < 5);
```
**Ausgabe:**
```
Zähler: 0
Zähler: 1
Zähler: 2
Zähler: 3
Zähler: 4
```

### Beispiel 2: Benutzereingabe mit do-Schleife
```java
import java.util.Scanner;

public class DoWhileExample {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String eingabe;

        do {
            System.out.println("Geben Sie 'exit' ein, um die Schleife zu beenden:");
            eingabe = scanner.nextLine();
        } while (!eingabe.equals("exit"));

        System.out.println("Schleife beendet.");
        scanner.close();
    }
}
```

## Erklärung
- **Häufige Fallstricke:** Ein häufiger Fehler ist, dass die Bedingung in der "do"-Schleife möglicherweise nie "false" wird, was zu einer Endlosschleife führt. Achten Sie darauf, dass die Bedingung korrekt formuliert ist und durch eine Logik im Code verändert wird.
- **Verwendung von break:** Sie können die Schleife jederzeit mit dem `break`-Befehl verlassen, unabhängig von der Bedingung.
- **Verwirrung mit while-Schleifen:** Anfänger verwechseln oft die "do"-Schleife mit der "while"-Schleife, da sie beide Schleifenstrukturen verwenden, um Code wiederholt auszuführen. Der Hauptunterschied ist, dass die "do"-Schleife garantiert mindestens einmal ausgeführt wird.

## Einzeiler Zusammenfassung
Die "do"-Schleife in Java garantiert die mindestens einmalige Ausführung eines Codeblocks, bevor die Schleifenbedingung überprüft wird.