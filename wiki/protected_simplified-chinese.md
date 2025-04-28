<!--
Meta Description: # Java中的protected关键字详解 ## 概述 在Java编程语言中，`protected`关键字用于控制类成员（变量和方法）的访问权限。它是四种访问修饰符之一，主要用于实现类的继承和包之间的访问控制。 ## 文档 ### 目的 `protected`修饰符允许同一个包中的其他类以及该类的...
Meta Keywords: protected, name, child, public, java
-->

# Java中的protected关键字详解

## 概述
在Java编程语言中，`protected`关键字用于控制类成员（变量和方法）的访问权限。它是四种访问修饰符之一，主要用于实现类的继承和包之间的访问控制。

## 文档
### 目的
`protected`修饰符允许同一个包中的其他类以及该类的子类访问其成员。这种机制促进了类之间的继承关系，使得子类可以访问父类中受保护的属性和方法。

### 使用
在Java中，`protected`关键字可以用于类的成员变量和方法。其基本语法如下：

```java
protected 数据类型 成员变量名;
protected 返回类型 方法名(参数列表) {
    // 方法体
}
```

### 细节
- **包访问权限**：`protected`成员可以被同一包中的其他类访问。
- **子类访问**：即使子类在不同的包中，`protected`成员也可以被访问。
- **与private的区别**：`private`成员只能在定义它的类内部访问，而`protected`则允许同一包中的其他类和子类访问。
- **与public的区别**：`public`成员可被任何类访问，而`protected`成员的访问权限较为限制。

## 示例
以下是使用`protected`关键字的基本示例：

```java
// 父类
class Parent {
    protected String name;

    protected void display() {
        System.out.println("Name: " + name);
    }
}

// 子类
class Child extends Parent {
    public void setName(String name) {
        this.name = name; // 访问父类的protected成员
    }

    public void show() {
        display(); // 访问父类的protected方法
    }
}

// 主类
public class Main {
    public static void main(String[] args) {
        Child child = new Child();
        child.setName("Java");
        child.show(); // 输出: Name: Java
    }
}
```

## 解释
- **常见问题**：初学者常常会混淆`protected`和`private`的使用，导致无法访问父类的成员。
- **注意事项**：在使用`protected`时，要注意包的关系。如果子类在不同的包中，确保适当地管理访问权限。
- **继承关系**：使用`protected`可以有效地促进类的继承和多态性，但不当使用可能导致设计上的复杂性。

## 简要总结
`protected`关键字在Java中用于控制类成员的访问，使得子类和同一包内的类可以访问这些成员。