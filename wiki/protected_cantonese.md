<!--
Meta Description: # Java 中的 "protected" 關鍵字：使用與特點 ## 概述 在 Java 程式設計中，`protected` 是一個訪問修飾符，用於控制類別成員（如變數和方法）的可見性。它允許同一包中的其他類別訪問，並且在子類別中也可以訪問，即使這些子類別位於不同的包中。 ## 文檔 `protec...
Meta Keywords: protected, java, child, class, void
-->

# Java 中的 "protected" 關鍵字：使用與特點

## 概述
在 Java 程式設計中，`protected` 是一個訪問修飾符，用於控制類別成員（如變數和方法）的可見性。它允許同一包中的其他類別訪問，並且在子類別中也可以訪問，即使這些子類別位於不同的包中。

## 文檔
`protected` 修飾符的主要目的是在封裝和繼承中提供靈活性。當一個成員變數或方法被聲明為 `protected` 時，它的訪問範圍如下：

- 同一包中的其他類別可以訪問。
- 不同包中的子類別可以訪問。

### 使用方法
要使用 `protected` 修飾符，只需在類別成員聲明之前加上 `protected` 關鍵字。例如：

```java
protected int myValue;
```

### 詳細資訊
- `protected` 主要用於類別的繼承，讓子類別能夠訪問父類別的成員。
- 如果類別成員沒有指定訪問修飾符，則默認為包私有（package-private），只允許同一包的類別訪問。
- `protected` 不能用於類別本身，只能用於成員變數和方法。

## 示例
以下是使用 `protected` 的基本範例：

```java
// 父類別
class Parent {
    protected void display() {
        System.out.println("這是父類別的方法");
    }
}

// 子類別
class Child extends Parent {
    public void show() {
        display(); // 可以訪問父類別的 protected 方法
    }
}

// 主程式
public class Main {
    public static void main(String[] args) {
        Child child = new Child();
        child.show(); // 輸出: 這是父類別的方法
    }
}
```

## 說明
- **常見陷阱**：在使用 `protected` 時要注意，這並不意味著類別的成員是完全公開的。它仍然受到包和繼承的限制。
- **跨包訪問**：只有當一個類別是另一個類別的子類別時，它才能訪問 `protected` 成員，這在不同包中是有效的。
- **不適合所有情況**：在某些情況下，過度使用 `protected` 可能會導致不必要的耦合，應根據需求謹慎使用。

## 總結
在 Java 中，`protected` 修飾符為類別成員提供了靈活的訪問控制，允許同一包和不同包中的子類別訪問。