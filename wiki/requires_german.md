<!--
Meta Description: # Das Schlüsselwort "requires" in Java: Eine umfassende Anleitung ## Synopsis Das Schlüsselwort `requires` in Java wird verwendet, um Modulabhängigkei...
Meta Keywords: module, modul, requires, java, dass
-->

# Das Schlüsselwort "requires" in Java: Eine umfassende Anleitung

## Synopsis
Das Schlüsselwort `requires` in Java wird verwendet, um Modulabhängigkeiten in der Modul-Ära von Java zu deklarieren, die mit Java 9 eingeführt wurde. Es beschreibt, welche anderen Module ein bestimmtes Modul benötigt, um korrekt zu funktionieren.

## Dokumentation
In Java 9 wurde das Modul-System eingeführt, um den Umgang mit großen Codebasen und Bibliotheken zu verbessern. Das `requires`-Schlüsselwort spielt eine zentrale Rolle in diesem System. Es wird in der Modul-Info-Datei (`module-info.java`) verwendet, um anzugeben, dass ein Modul auf ein anderes Modul angewiesen ist.

### Zweck
Der Hauptzweck des `requires`-Befehls ist die Definition von Abhängigkeiten zwischen Modulen. Dies ermöglicht eine bessere Kapselung und Modularisierung des Codes, indem klar definiert wird, welche Module auf andere zugreifen können.

### Verwendung
Die Verwendung des `requires`-Schlüsselworts erfolgt in der `module-info.java`-Datei eines Moduls. Hier ist ein einfaches Beispiel:

```java
module mein.modul {
    requires anderes.modul;
}
```

In diesem Beispiel gibt das Modul `mein.modul` an, dass es auf `anderes.modul` angewiesen ist. Dadurch wird sichergestellt, dass alle erforderlichen Abhängigkeiten zur Kompilierzeit und Laufzeit verfügbar sind.

### Details
- **Transitive Abhängigkeiten**: Mit `requires transitive` können Module auch angeben, dass die Abhängigkeit für alle Module, die dieses Modul verwenden, ebenfalls verfügbar sein muss:
  
  ```java
  module mein.modul {
      requires transitive anderes.modul;
  }
  ```

- **Optionale Abhängigkeiten**: Es gibt keine direkte Möglichkeit, optionale Abhängigkeiten im Modul-System zu deklarieren. Entwickler müssen ihre Module so gestalten, dass sie mit oder ohne bestimmte Abhängigkeiten funktionieren.

## Beispiele
Hier sind einige grundlegende Beispiele für die Verwendung des `requires`-Schlüsselworts:

1. **Einfaches Modul mit einer Abhängigkeit**:
   ```java
   module app {
       requires logging.module;
   }
   ```

2. **Modul mit transitive Abhängigkeit**:
   ```java
   module app {
       requires transitive database.module;
   }
   ```

3. **Mehrere Abhängigkeiten**:
   ```java
   module app {
       requires logging.module;
       requires database.module;
   }
   ```

## Erklärung
Ein häufiges Missverständnis besteht darin, dass `requires` nur für die Kompilierung von Bedeutung ist. Tatsächlich stellt `requires` auch sicher, dass zur Laufzeit alle Module vorhanden sind. Ein weiterer Fallstrick ist das Vergessen der `module-info.java`-Datei oder das falsche Deklarieren von Abhängigkeiten, was zu Laufzeitfehlern führen kann.

Es ist wichtig zu beachten, dass die Importierung von Paketen innerhalb eines Moduls nicht automatisch bedeutet, dass alle Abhängigkeiten korrekt behandelt werden. Der Entwickler muss sicherstellen, dass alle benötigten Module korrekt deklariert sind.

## Ein-Satz-Zusammenfassung
Das `requires`-Schlüsselwort in Java definiert Modulabhängigkeiten und sorgt für eine klare Strukturierung und Modularisierung des Codes in der Java-Entwicklung.