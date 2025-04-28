<!--
Meta Description: # Java 中的 "protected" 關鍵字：理解其使用和特性 ## 概述 在 Java 程式設計中，`protected` 是一個存取修飾符，用於控制類別成員（屬性和方法）的可見性。它允許同一個包內的其他類別和所有子類別訪問該成員，從而提供了一種靈活的封裝機制。 ## 文檔 ### 目的 `...
Meta Keywords: protected, java, child, age, void
-->

# Java 中的 "protected" 關鍵字：理解其使用和特性

## 概述
在 Java 程式設計中，`protected` 是一個存取修飾符，用於控制類別成員（屬性和方法）的可見性。它允許同一個包內的其他類別和所有子類別訪問該成員，從而提供了一種靈活的封裝機制。

## 文檔
### 目的
`protected` 修飾符的主要目的是增強物件導向程式設計中的封裝性，同時又不完全限制對類別成員的訪問。這使得子類別可以在繼承父類別時，繼續使用和擴展父類別的功能。

### 使用
在定義類別成員時，可以使用 `protected` 修飾符。其語法如下：
```java
protected 返回類型 成員名稱;
```
例如：
```java
protected int age;
protected void display() {
    System.out.println("Age: " + age);
}
```
在這個例子中，`age` 屬性和 `display` 方法都是 `protected`，這意味著它們可以被同一個包中的其他類別以及所有子類別訪問。

### 詳細信息
1. **可見性範圍**：`protected` 成員可以被同一包內的類別訪問，也可以被任何繼承該類別的子類別訪問，即使這些子類別位於不同的包中。
2. **與其他修飾符的比較**：
   - `public`：可以被任何類別訪問。
   - `private`：只能在定義它的類別內部訪問。
   - 默認（未使用任何修飾符）：只能在同一個包內訪問。

## 範例
以下是一個使用 `protected` 關鍵字的簡單範例：

```java
class Parent {
    protected void showMessage() {
        System.out.println("This is a protected method.");
    }
}

class Child extends Parent {
    void display() {
        showMessage();  // 可以訪問父類中的 protected 方法
    }
}

public class Test {
    public static void main(String[] args) {
        Child child = new Child();
        child.display();  // 輸出：This is a protected method.
    }
}
```

## 解釋
### 常見陷阱與注意事項
- **包外訪問限制**：儘管 `protected` 允許子類別訪問，但如果該子類別不在同一包中，則無法直接訪問 `protected` 成員，必須通過實例來訪問。
- **接口與 `protected`**：在接口中定義的方法默認為 `public`，因此不能使用 `protected` 修飾符。
- **抽象類別**：在抽象類別中使用 `protected` 方法時，子類別必須實現這些方法，否則將無法編譯。

## 一句總結
在 Java 中，`protected` 修飾符允許類別成員在同一包內及其子類別中訪問，從而實現靈活的封裝和繼承。