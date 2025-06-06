<!--
Meta Description: # 非密封 (non-sealed) 在 JAVA 中的應用 ## 簡介 在 JAVA 17 中引入的「非密封」關鍵字 (non-sealed) 是一種用於類和介面的修飾符，旨在提供更多靈活性和擴展性。它允許其他類從密封類或密封介面繼承，而不受密封的限制。 ## 文檔 「非密封」關鍵字的主要目的是打...
Meta Keywords: 非密封, java, sealed, non, circle
-->

# 非密封 (non-sealed) 在 JAVA 中的應用

## 簡介
在 JAVA 17 中引入的「非密封」關鍵字 (non-sealed) 是一種用於類和介面的修飾符，旨在提供更多靈活性和擴展性。它允許其他類從密封類或密封介面繼承，而不受密封的限制。

## 文檔
「非密封」關鍵字的主要目的是打破密封類的限制，讓開發者能夠創建更靈活的繼承結構。當一個類被標記為非密封時，這意味著任何類都可以從這個類繼承，無論這些類是否在同一個模組或包中。

### 用法
在 JAVA 中，使用「non-sealed」關鍵字的語法如下：

```java
non-sealed class ClassName { 
    // 類的實現 
}
```

這樣，`ClassName` 可以被任何其他類繼承。

### 詳細信息
- 「非密封」類型必須繼承自一個密封類或密封介面。
- 在一個密封的類中，所有的子類必須明確地列出，這樣一來，開發者可以控制繼承層次結構。而「非密封」則不會這樣限制。
- 在密封類和介面中，可以有多種子類，這些子類可以是密封的、非密封的或開放的。

## 示例
以下是如何在 JAVA 中使用「非密封」關鍵字的基本示例：

```java
sealed class Shape permits Circle, Square {}

non-sealed class Circle extends Shape {
    // Circle 的具體實現
}

class Square extends Shape {
    // Square 的具體實現
}
```

在上面的例子中，`Shape` 是一個密封類，只允許 `Circle` 和 `Square` 繼承。`Circle` 是一個非密封類，因此任何其他類都能從它繼承。

## 解釋
使用「非密封」關鍵字時，開發者需注意以下幾點：

- **設計考量**：雖然「非密封」提供了靈活性，但過度使用可能導致繼承結構變得複雜，影響代碼的可讀性和可維護性。
- **安全性**：在某些情況下，允許任意類繼承可能會引入安全性問題，開發者需要仔細考慮這種設計選擇。
- **性能考量**：不當使用「非密封」可能影響運行性能，尤其是在大規模應用中。

## 一句話總結
「非密封」關鍵字在 JAVA 中提供了靈活的繼承機制，允許開發者突破密封類的限制。