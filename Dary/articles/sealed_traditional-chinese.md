<!--
Meta Description: # Java 中的 Sealed 類別：定義與使用 ## 簡介 在 Java 17 中引入的 Sealed 類別允許開發者控制哪些類別可以擴展或實作某個類別或介面。這一特性有助於增強程式碼的安全性與可維護性，並提供了更好的類別設計選擇。 ## 文檔 ### 目的 Sealed 類別的主要目的是限制類...
Meta Keywords: sealed, public, shape, circle, square
-->

# Java 中的 Sealed 類別：定義與使用

## 簡介
在 Java 17 中引入的 Sealed 類別允許開發者控制哪些類別可以擴展或實作某個類別或介面。這一特性有助於增強程式碼的安全性與可維護性，並提供了更好的類別設計選擇。

## 文檔
### 目的
Sealed 類別的主要目的是限制類別的繼承層級，讓開發者能夠明確指定哪些類別是合法的擴展者。這對於某些應用場景，如保持 API 的穩定性或設計符合特定規範的類別結構時，尤為重要。

### 使用方式
要定義一個 Sealed 類別，使用 `sealed` 關鍵字，並指定允許擴展的類別或介面。下面是語法示例：

```java
public sealed class Shape permits Circle, Square {
    // 類別內容
}

public final class Circle extends Shape {
    // Circle 類別內容
}

public final class Square extends Shape {
    // Square 類別內容
}
```

在上述範例中，`Shape` 類別是 Sealed 類別，只允許 `Circle` 和 `Square` 這兩個類別擴展。

### 詳細說明
- **Sealed 類別的特性**：
  - 只能使用 `final`、`non-sealed` 或其他 Sealed 類別作為允許擴展的類別。
  - 這樣的設計可以防止在不預期的情況下進行擴展，進一步增強了類別的控制性。

- **使用的限制**：
  - Sealed 類別必須定義在同一個檔案中。
  - 只能在同一個模塊中進行擴展，這意味著所有允許的類別必須在相同的模塊中定義。

## 範例
以下是 Sealed 類別的基本使用範例：

```java
// Sealed 類別 Shape
public sealed class Shape permits Circle, Square {
    public abstract double area();
}

// Circle 類別
public final class Circle extends Shape {
    private final double radius;

    public Circle(double radius) {
        this.radius = radius;
    }

    @Override
    public double area() {
        return Math.PI * radius * radius;
    }
}

// Square 類別
public final class Square extends Shape {
    private final double side;

    public Square(double side) {
        this.side = side;
    }

    @Override
    public double area() {
        return side * side;
    }
}
```

## 解釋
### 常見陷阱
- **未使用 permits 關鍵字**：如果未正確使用 `permits` 關鍵字，將無法正確限制繼承的類別。
- **不支持多重繼承**：Sealed 類別不支援多重繼承，這在設計時需要特別注意，以免引入不必要的複雜性。
- **繼承層級的限制**：開發者必須在設計階段仔細考慮哪些類別應該被允許擴展，以避免未來修改帶來的困難。

## 一句總結
Sealed 類別是 Java 中一個強大的特性，允許開發者控制類別的繼承，從而提升程式碼的安全性和可維護性。