<!--
Meta Description: # Java 中的 Record：简化数据类的定义与使用 ## 摘要 在 Java 14 及以后的版本中，引入了 Record 关键字，旨在简化不可变数据类的定义。Record 提供了一种简洁的语法来创建用于存储数据的数据类，自动生成构造函数、访问器和其他常用方法。 ## 文档 ### 目的 Rec...
Meta Keywords: record, person, java, string, name
-->

# Java 中的 Record：简化数据类的定义与使用

## 摘要
在 Java 14 及以后的版本中，引入了 Record 关键字，旨在简化不可变数据类的定义。Record 提供了一种简洁的语法来创建用于存储数据的数据类，自动生成构造函数、访问器和其他常用方法。

## 文档
### 目的
Record 的主要目的是简化 Java 中数据传输对象（DTO）或简单数据类的创建过程。使用 Record，可以减少样板代码，使得代码更加清晰且易于维护。

### 用法
使用 Record 定义一个数据类非常简单。只需使用 `record` 关键字，后跟类名和构造函数参数列表。Record 会自动为您生成访问器方法（getters）、`toString`、`equals` 和 `hashCode` 方法。

### 详细说明
```java
record Person(String name, int age) {}
```
在上面的例子中，`Person` 是一个 Record 类型，包含两个字段：`name` 和 `age`。这个定义自动生成了如下方法：
- `String name()`
- `int age()`
- `String toString()`
- `boolean equals(Object o)`
- `int hashCode()`

Record 也可以实现接口，并且可以有附加字段和方法，但它们的字段必须是 final 的，且一旦创建，不能被修改。

## 示例
### 基本用法
```java
public class Main {
    public static void main(String[] args) {
        Person person = new Person("Alice", 30);
        System.out.println(person.name()); // 输出: Alice
        System.out.println(person.age());  // 输出: 30
        System.out.println(person);         // 输出: Person[name=Alice, age=30]
    }
}
```

### 带方法的 Record
```java
record Circle(double radius) {
    double area() {
        return Math.PI * radius * radius;
    }
}

public class Main {
    public static void main(String[] args) {
        Circle circle = new Circle(5);
        System.out.println(circle.area()); // 输出: 78.53981633974483
    }
}
```

## 解释
尽管 Record 提供了很多便利，但仍需注意以下几点：
- Record 只能用于不可变的数据结构，所有字段都必须是 final。
- Record 不能扩展其他类，但可以实现接口。
- 不能直接修改 Record 中的字段，必须通过创建新的 Record 实例来更改数据。

使用 Record 时，确保理解它的不可变性和与传统类的差异，以避免潜在的误解。

## 一句话总结
Java 的 Record 是一种用于简化数据类定义的功能，自动生成常见方法，提升代码可读性和可维护性。