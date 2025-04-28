<!--
Meta Description: # Sealed 類別在 JAVA 中的應用 ## 概述 在 JAVA 中，"sealed" 是一種新引入的類別修飾符，旨在提高編譯時的類別繼承控制，從而增強代碼的安全性和可維護性。它允許開發者限制哪些類別可以擴展或實現某個類別，進一步減少意外的多態性。 ## 文檔 ### 目的 "sealed" ...
Meta Keywords: sealed, class, public, 類的內容, java
-->

# Sealed 類別在 JAVA 中的應用

## 概述
在 JAVA 中，"sealed" 是一種新引入的類別修飾符，旨在提高編譯時的類別繼承控制，從而增強代碼的安全性和可維護性。它允許開發者限制哪些類別可以擴展或實現某個類別，進一步減少意外的多態性。

## 文檔
### 目的
"sealed" 修飾符的主要目的是限制哪些類別可以繼承某個父類別。這可以有效地控制類別的繼承層級，確保只有特定的類別能夠擴展父類別，從而達到更嚴格的類別設計。

### 使用方法
要使用 "sealed"，只需在類別聲明時添加 `sealed` 修飾符，並指定允許繼承的子類別。以下是基本語法：

```java
public sealed class ParentClass permits ChildClass1, ChildClass2 {
    // 類的內容
}
```

在這個示例中，`ParentClass` 是一個密封類別，只有 `ChildClass1` 和 `ChildClass2` 可以繼承它。

### 詳細說明
- **密封類別** (sealed class): 用於限制其他類別的繼承。
- **許可類別** (permits): 用於列出所有允許繼承的子類別。
- **非密封類別** (non-sealed): 允許其他類別進一步繼承的類別。
- **封閉類別** (final): 無法被任何類別繼承。

## 示例
### 基本用法示例
以下是如何使用 `sealed` 類別的簡單示例：

```java
public sealed class Shape permits Circle, Square {
    // 類的內容
}

public final class Circle extends Shape {
    // 類的內容
}

public final class Square extends Shape {
    // 類的內容
}
```

在這個例子中，`Shape` 是一個密封類別，只有 `Circle` 和 `Square` 可以繼承它。

### 非密封類別示例
```java
public sealed class Vehicle permits Car, Truck {
    // 類的內容
}

public non-sealed class Car extends Vehicle {
    // 類的內容
}

public final class Truck extends Vehicle {
    // 類的內容
}
```
在這個示例中，`Car` 是一個非密封類別，可以被其他類別繼承，而 `Truck` 則是一個封閉類別，無法被繼承。

## 解釋
在使用 "sealed" 時，開發者需要注意以下幾點：
1. **繼承限制**: 確保在 `permits` 中列出的類別都是正確的，否則將導致編譯錯誤。
2. **可維護性**: 密封類別的設計需謹慎，因為一旦設計完成，後續的擴展可能會受到限制。
3. **結構清晰**: 使用 "sealed" 有助於清晰地表達類別之間的關係，減少不必要的繼承。

## 一行總結
在 JAVA 中，"sealed" 修飾符用於限制類別的繼承，增強代碼的安全性和結構性。