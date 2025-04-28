<!--
Meta Description: # Java中的“super”关键字详解 ## 简介 在Java编程中，“super”关键字用于引用当前对象的父类（超类）成员，包括字段和方法。它是实现继承和多态性的关键工具，帮助开发者在子类中访问父类的特性。 ## 文档说明 ### 目的 “super”关键字主要用于以下几种情况： 1. 调用父类...
Meta Keywords: super, child, class, parent, system
-->

# Java中的“super”关键字详解

## 简介
在Java编程中，“super”关键字用于引用当前对象的父类（超类）成员，包括字段和方法。它是实现继承和多态性的关键工具，帮助开发者在子类中访问父类的特性。

## 文档说明
### 目的
“super”关键字主要用于以下几种情况：
1. 调用父类的构造方法。
2. 访问父类的字段或方法，特别是当子类中存在同名成员时。
3. 实现多态性，确保调用的是父类的实现。

### 使用方式
- **调用父类构造方法**：使用`super()`语法。
- **访问父类字段**：使用`super.fieldName`。
- **调用父类方法**：使用`super.methodName()`。

### 详细说明
在Java中，子类可以继承父类的属性和方法，但当子类中与父类有相同名称的成员时，子类的成员会隐藏父类的成员。在这种情况下，使用“super”可以明确访问父类的成员。此外，“super”关键字也可以用于调用父类的构造函数，以确保父类的初始化。

## 示例
### 示例1：调用父类构造方法
```java
class Parent {
    Parent() {
        System.out.println("父类构造方法");
    }
}

class Child extends Parent {
    Child() {
        super(); // 调用父类构造方法
        System.out.println("子类构造方法");
    }
}

public class Test {
    public static void main(String[] args) {
        Child child = new Child();
    }
}
```
**输出：**
```
父类构造方法
子类构造方法
```

### 示例2：访问父类字段
```java
class Parent {
    String name = "父类名字";
}

class Child extends Parent {
    String name = "子类名字";

    void display() {
        System.out.println("父类名字: " + super.name); // 访问父类字段
        System.out.println("子类名字: " + name); // 访问子类字段
    }
}

public class Test {
    public static void main(String[] args) {
        Child child = new Child();
        child.display();
    }
}
```
**输出：**
```
父类名字: 父类名字
子类名字: 子类名字
```

### 示例3：调用父类方法
```java
class Parent {
    void display() {
        System.out.println("父类方法");
    }
}

class Child extends Parent {
    void display() {
        super.display(); // 调用父类方法
        System.out.println("子类方法");
    }
}

public class Test {
    public static void main(String[] args) {
        Child child = new Child();
        child.display();
    }
}
```
**输出：**
```
父类方法
子类方法
```

## 说明
- **常见陷阱**：在使用“super”时，请确保父类构造方法的调用在子类构造方法的第一行。
- **重载与重写**：当方法被重写时，可以使用“super”调用父类的被重写方法。
- **静态上下文**：注意，静态方法不能通过“super”调用父类的实例方法。

## 一句话总结
在Java中，“super”关键字用于访问父类的构造方法、字段和方法，是实现继承和多态性的核心工具。