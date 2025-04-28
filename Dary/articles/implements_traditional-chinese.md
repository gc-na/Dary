<!--
Meta Description: # 在 Java 中的 "implements" 關鍵字：介面實作的詳細指南 ## 概要 在 Java 程式語言中，`implements` 關鍵字用於實作介面，使得類別能夠遵循介面所定義的方法規範。這是物件導向程式設計中的一個重要概念，允許類別之間的多重繼承和行為約定。 ## 文檔 ### 目的 ...
Meta Keywords: implements, java, class, dog, animal
-->

# 在 Java 中的 "implements" 關鍵字：介面實作的詳細指南

## 概要
在 Java 程式語言中，`implements` 關鍵字用於實作介面，使得類別能夠遵循介面所定義的方法規範。這是物件導向程式設計中的一個重要概念，允許類別之間的多重繼承和行為約定。

## 文檔
### 目的
`implements` 關鍵字的主要目的是讓類別實作一個或多個介面，確保類別提供介面中定義的所有方法。這樣不僅促進了代碼的可重用性，也提高了系統的可擴展性。

### 使用方式
當一個類別實作介面時，必須使用 `implements` 關鍵字並提供介面中定義的所有方法的具體實現。以下是基本語法：

```java
class ClassName implements InterfaceName {
    // 實作介面方法
}
```

如果一個類別需要實作多個介面，可以使用逗號分隔它們，如下所示：

```java
class ClassName implements InterfaceOne, InterfaceTwo {
    // 實作介面方法
}
```

### 詳情
- **介面定義**：介面是一種特殊的類型，不能直接實例化。它們通常包含方法的簽名，但不提供具體的實現。
- **多重介面實作**：Java 支持一個類別實作多個介面，這使得開發者可以以更靈活的方式設計類別。
- **缺省方法**：從 Java 8 開始，介面可以包含缺省方法的實現，這意味著類別不必每次都實作這些方法。

## 示例
以下是一個簡單的示範，展示如何使用 `implements` 來實作介面：

```java
// 定義介面
interface Animal {
    void sound();
}

// 實作介面
class Dog implements Animal {
    @Override
    public void sound() {
        System.out.println("汪汪");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal dog = new Dog();
        dog.sound(); // 輸出：汪汪
    }
}
```

## 解釋
- **常見陷阱**：當實作介面時，確保類別中實現了所有介面方法，否則編譯器將會報錯。
- **方法簽名**：實作的方法簽名必須完全匹配介面中定義的方法，包含返回類型和參數。
- **抽象類別的區別**：雖然抽象類別也可以包含未實作的方法，但它們可以包含具體的實現，而介面主要專注於定義行為。

## 一句總結
`implements` 關鍵字在 Java 中用於讓類別實作介面，確保類別遵循介面所定義的行為規範。