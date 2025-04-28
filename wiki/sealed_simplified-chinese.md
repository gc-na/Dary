<!--
Meta Description: # Java中的密封类（sealed classes）特性详解 ## 概述 在Java中，密封类（sealed classes）是一种新特性，旨在增强类型系统的表达能力和安全性。它允许开发者限制哪些类可以扩展或实现特定类或接口，从而提供更严格的继承控制。 ## 文档 密封类的目的是控制哪些子类可以继...
Meta Keywords: sealed, public, class, final, permits
-->

# Java中的密封类（sealed classes）特性详解

## 概述
在Java中，密封类（sealed classes）是一种新特性，旨在增强类型系统的表达能力和安全性。它允许开发者限制哪些类可以扩展或实现特定类或接口，从而提供更严格的继承控制。

## 文档
密封类的目的是控制哪些子类可以继承或实现某个类。这一特性在Java 15中以预览特性形式引入，并在Java 17中正式成为标准特性。密封类的主要用途包括：

- **增强安全性**：通过限制继承，避免未授权的类型扩展。
- **清晰的API设计**：开发者可以明确指定哪些类是可扩展的，从而改善代码的可读性和可维护性。
- **模式匹配支持**：与密封类结合，Java的模式匹配可以更加安全和明确。

### 使用方法
要定义一个密封类，可以使用`sealed`关键字，后跟`permits`指定允许继承的子类。例如：

```java
public sealed class Shape permits Circle, Rectangle {
    // 类体
}

public final class Circle extends Shape {
    // 类体
}

public final class Rectangle extends Shape {
    // 类体
}
```

在上面的示例中，`Shape`是一个密封类，它只允许`Circle`和`Rectangle`作为其子类。

## 示例
以下是一个使用密封类的基本示例：

```java
public sealed class Vehicle permits Car, Truck {
    // 类体
}

public final class Car extends Vehicle {
    // 类体
}

public final class Truck extends Vehicle {
    // 类体
}
```

此示例中，`Vehicle`是一个密封类，仅允许`Car`和`Truck`作为其子类。

## 说明
- **限制**：密封类必须是`public`或`protected`，并且只能被`final`、`sealed`或`non-sealed`的子类继承。
- **常见错误**：如果尝试从未在`permits`中声明的类扩展密封类，会导致编译错误。
- **设计考量**：在设计API时，使用密封类可以帮助更好地控制继承层次，并确保API的一致性和安全性。

## 一句话总结
密封类（sealed classes）是Java中的一种特性，用于限制类的继承，增强类型安全和API设计清晰度。