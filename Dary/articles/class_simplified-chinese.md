<!--
Meta Description: # Java 类 (Class)：面向对象编程的核心 ## 概述 在Java编程语言中，类是创建对象的模板或蓝图。它定义了对象的属性（字段）和行为（方法）。类是面向对象编程的基本构建块，使得代码更加模块化和可重用。 ## 文档 ### 目的 类用于封装数据和方法，提供一个结构化的方式来组织代码。通过...
Meta Keywords: public, student, private, int, name
-->

# Java 类 (Class)：面向对象编程的核心

## 概述
在Java编程语言中，类是创建对象的模板或蓝图。它定义了对象的属性（字段）和行为（方法）。类是面向对象编程的基本构建块，使得代码更加模块化和可重用。

## 文档
### 目的
类用于封装数据和方法，提供一个结构化的方式来组织代码。通过使用类，开发者可以创建可重用的代码片段，从而提高开发效率和代码的可维护性。

### 用法
在Java中定义一个类的基本语法如下：

```java
public class ClassName {
    // 字段
    private int fieldName;

    // 构造器
    public ClassName(int value) {
        this.fieldName = value;
    }

    // 方法
    public int getFieldName() {
        return fieldName;
    }
}
```

以上示例展示了如何定义一个简单的类，包括私有字段、构造器和方法。可以通过创建类的实例来访问这些方法和字段。

### 详细说明
1. **类的定义**：Java类使用`class`关键字定义，类名应遵循驼峰命名法。
2. **字段**：字段是类的属性，通常是私有的（使用`private`修饰符），以保护数据的封装性。
3. **构造器**：构造器是特殊的方法，用于初始化对象的状态。构造器的名称与类名相同，没有返回类型。
4. **方法**：类中的方法定义了对象的行为。

## 示例
以下是一个简单的Java类示例，表示一个“学生”类：

```java
public class Student {
    private String name;
    private int age;

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public void displayInfo() {
        System.out.println("姓名: " + name + ", 年龄: " + age);
    }

    public static void main(String[] args) {
        Student student = new Student("张三", 20);
        student.displayInfo();
    }
}
```

在这个示例中，我们定义了一个`Student`类，并在`main`方法中创建了一个`Student`对象。

## 说明
- **常见陷阱**：在Java中，类名和文件名必须匹配，确保文件名与类名一致。
- **访问修饰符**：了解`public`、`private`、`protected`的使用，以确保数据的封装性和安全性。
- **继承和多态**：类是继承和多态的基础，理解如何使用`extends`关键字和方法重载是非常重要的。

## 一句话总结
Java类是面向对象编程的基本构建块，定义了对象的属性和行为。