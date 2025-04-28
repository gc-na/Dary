<!--
Meta Description: # Java中的默认关键字详解 ## 概述 在Java编程语言中，`default`关键字用于指定接口中的默认方法。这一特性在Java 8中引入，允许开发者为接口提供默认实现，从而在不破坏现有实现的情况下扩展接口。 ## 文档 ### 目的 `default`关键字的主要目的是为接口中的方法提供一个...
Meta Keywords: public, default, dog, void, system
-->

# Java中的默认关键字详解

## 概述
在Java编程语言中，`default`关键字用于指定接口中的默认方法。这一特性在Java 8中引入，允许开发者为接口提供默认实现，从而在不破坏现有实现的情况下扩展接口。

## 文档
### 目的
`default`关键字的主要目的是为接口中的方法提供一个默认实现，使得实现该接口的类可以直接使用这些方法而无需在每个类中重新定义它们。这对于向现有接口添加新功能非常有用。

### 用法
在接口中，您可以使用`default`关键字来定义一个方法。一个示例接口如下：

```java
public interface MyInterface {
    default void myDefaultMethod() {
        System.out.println("这是一个默认方法");
    }
}
```

实现该接口的类可以选择使用默认方法，或者覆盖它来提供自己的实现：

```java
public class MyClass implements MyInterface {
    @Override
    public void myDefaultMethod() {
        System.out.println("重写的默认方法");
    }
}
```

### 细节
- 默认方法可以有方法体，也可以没有（即可以是抽象的）。
- 如果一个类实现了多个接口，并且这些接口中有同名的默认方法，类必须重写该方法以消除冲突。
- 默认方法可以访问接口中的其他静态方法和常量。

## 示例
以下是一个简单的示例，展示了如何使用`default`关键字：

```java
public interface Animal {
    default void sound() {
        System.out.println("动物发出声音");
    }
}

public class Dog implements Animal {
    public void sound() {
        System.out.println("汪汪");
    }
}

public class Test {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.sound(); // 输出: 汪汪
    }
}
```

在这个示例中，`Dog`类实现了`Animal`接口，并重写了`sound`方法。

## 解释
- **常见陷阱**：确保在实现多个接口时，正确处理重写冲突。否则，编译器会提示错误。
- **额外注意**：默认方法只能在接口中定义，不能在类中使用。

## 一句话总结
`default`关键字在Java中用于为接口提供默认方法实现，从而增强接口的灵活性和可扩展性。