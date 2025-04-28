<!--
Meta Description: # Java 非密封類別 (non-sealed classes) 的用法與特性 ## 概述 在 Java 17 中引入的非密封類別（non-sealed classes）是一種允許開發者在定義類別時放寬密封性限制的功能。這一特性使得開發者能夠更靈活地擴展密封類別，從而提高了代碼的可擴展性和可維護性...
Meta Keywords: sealed, non, public, class, circle
-->

# Java 非密封類別 (non-sealed classes) 的用法與特性

## 概述
在 Java 17 中引入的非密封類別（non-sealed classes）是一種允許開發者在定義類別時放寬密封性限制的功能。這一特性使得開發者能夠更靈活地擴展密封類別，從而提高了代碼的可擴展性和可維護性。

## 文件說明
非密封類別是一種特殊的類別聲明，使用 `non-sealed` 關鍵字來標識。這意味著任何從該非密封類別繼承的子類別不再受到密封類別的限制，開發者可以自由地擴展其功能。這一特性是與密封類別（sealed classes）相對的，後者限制了可以繼承的類別。

### 用途
- **擴展性**：允許其他類別無限制地繼承非密封類別，適合需要進一步擴展的情境。
- **靈活性**：開發者可以選擇哪些類別是可擴展的，不必強制所有情況下都使用密封類別。

### 使用方式
要定義一個非密封類別，您需要在類別聲明中使用 `non-sealed` 關鍵字，示例如下：

```java
public sealed class Animal permits Dog, Cat {
    // 類別內容
}

public non-sealed class Dog extends Animal {
    // Dog 的實現
}

public class Cat extends Animal {
    // Cat 的實現
}
```

在上述示例中，`Animal` 是一個密封類別，而 `Dog` 是一個非密封類別，這意味著其他類別可以從 `Dog` 繼續繼承。

## 範例
以下是一個簡單的範例，演示如何使用非密封類別：

```java
public sealed class Shape permits Circle, Square {}

public non-sealed class Circle extends Shape {
    // Circle 的實現
}

public class Square extends Shape {
    // Square 的實現
}

// 其他類別可以從 Circle 繼承
public class ColoredCircle extends Circle {
    // ColoredCircle 的實現
}
```

在這個範例中，`Circle` 是非密封的，因此 `ColoredCircle` 可以繼承自 `Circle`，而不會受到限制。

## 解釋
在使用非密封類別時，開發者需要注意以下幾點：
- **結構清晰**：雖然非密封類別提供了靈活性，但過度使用可能導致代碼結構變得複雜，建議在必要時使用。
- **性能考量**：非密封類別的擴展可能會影響性能，特別是在層級深的繼承關係中。

## 總結
Java 的非密封類別（non-sealed classes）提供了靈活的繼承選擇，使開發者能夠在需要擴展的情況下更自由地設計其類別結構。