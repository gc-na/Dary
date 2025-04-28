<!--
Meta Description: # Der "continue"-Befehl in Java: Verwendung und Beispiele ## Synopsis Der "continue"-Befehl in Java wird verwendet, um die aktuelle Iteration einer Sc...
Meta Keywords: der, continue, die, schleife, befehl
-->

# Der "continue"-Befehl in Java: Verwendung und Beispiele

## Synopsis
Der "continue"-Befehl in Java wird verwendet, um die aktuelle Iteration einer Schleife vorzeitig zu beenden und mit der nächsten Iteration fortzufahren. Er ist in Schleifen wie for, while und do-while nützlich, um bestimmte Bedingungen zu überprüfen und die Ausführung zu steuern.

## Dokumentation
Der "continue"-Befehl in Java ist ein Steuerbefehl, der in Schleifen eingesetzt wird, um die Ausführung der Schleife zu beeinflussen. Wenn der "continue"-Befehl erreicht wird, überspringt die Schleife den restlichen Code in der aktuellen Iteration und fährt mit der nächsten Iteration fort. Der "continue"-Befehl kann auch mit einem Label verwendet werden, um spezifische Schleifen zu beeinflussen, wenn mehrere verschachtelte Schleifen vorhanden sind.

### Verwendung
- **Syntax:** 
  ```java
  continue; // Für die aktuelle Schleife
  continue; // Labelname; // Für die benannte Schleife
  ```

- **Gültigkeit:** 
  Der Befehl kann in for-, while- und do-while-Schleifen verwendet werden.

## Beispiele
Hier sind einige einfache Beispiele für die Verwendung des "continue"-Befehls in Java:

### Beispiel 1: Verwendung in einer for-Schleife
```java
public class ContinueExample {
    public static void main(String[] args) {
        for (int i = 0; i < 10; i++) {
            if (i % 2 == 0) {
                continue; // überspringt die geraden Zahlen
            }
            System.out.println(i); // gibt nur ungerade Zahlen aus
        }
    }
}
```

### Beispiel 2: Verwendung in einer while-Schleife
```java
public class ContinueExample {
    public static void main(String[] args) {
        int i = 0;
        while (i < 10) {
            i++;
            if (i == 5) {
                continue; // überspringt die Zahl 5
            }
            System.out.println(i); // gibt 1, 2, 3, 4, 6, 7, 8, 9, 10 aus
        }
    }
}
```

### Beispiel 3: Verwendung mit Label
```java
public class ContinueWithLabel {
    public static void main(String[] args) {
        outerLoop:
        for (int i = 0; i < 3; i++) {
            for (int j = 0; j < 3; j++) {
                if (j == 1) {
                    continue outerLoop; // überspringt die innere Schleife und geht zur nächsten äußeren Schleife
                }
                System.out.println("i = " + i + ", j = " + j);
            }
        }
    }
}
```

## Erklärung
Der "continue"-Befehl kann für Anfänger verwirrend sein, insbesondere in verschachtelten Schleifen. Es ist wichtig, sicherzustellen, dass die Verwendung von "continue" die gewünschte Logik der Schleife nicht beeinflusst. Ein häufiger Fehler ist, dass Programmierer annehmen, dass der "continue"-Befehl nur die innere Schleife beeinflusst, wenn er nicht mit einem Label verwendet wird. Außerdem kann das übermäßige Nutzen von "continue" den Code schwer lesbar machen, daher sollte er mit Bedacht eingesetzt werden.

## Einzeilige Zusammenfassung
Der "continue"-Befehl in Java ermöglicht es, die aktuelle Iteration einer Schleife zu überspringen und mit der nächsten zu fortzufahren.