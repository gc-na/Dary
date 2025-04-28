<!--
Meta Description: # Java中的while循环语句 ## 摘要 `while`循环是Java编程语言中用于实现重复执行代码块的重要控制结构。它在满足特定条件时，会持续执行代码，直到条件不再成立为止。 ## 文档 ### 目的 `while`循环用于在条件为真时重复执行一段代码。这在需要根据动态条件进行迭代时非常有用...
Meta Keywords: while, scanner, java, system, out
-->

# Java中的while循环语句

## 摘要
`while`循环是Java编程语言中用于实现重复执行代码块的重要控制结构。它在满足特定条件时，会持续执行代码，直到条件不再成立为止。

## 文档
### 目的
`while`循环用于在条件为真时重复执行一段代码。这在需要根据动态条件进行迭代时非常有用。

### 使用方法
`while`循环的基本语法如下：
```java
while (条件) {
    // 循环体
}
```
- **条件**：一个布尔表达式，决定循环是否继续执行。
- **循环体**：在条件为真时执行的代码块。

### 详细说明
- `while`循环首先评估条件。如果条件为真，执行循环体，然后再次评估条件，直到条件为假。
- 循环体可能包含多个语句，也可以是其他控制结构。
- 如果条件在第一次评估时为假，则循环体将不会执行。

## 示例
### 基本用法示例
以下是一个简单的`while`循环示例：
```java
int i = 0;
while (i < 5) {
    System.out.println("当前值: " + i);
    i++;
}
```
在这个例子中，`while`循环会打印`i`的值，直到`i`等于5。

### 另一示例
下面的示例展示了一个`while`循环的使用，读取用户输入直到输入为"exit"：
```java
import java.util.Scanner;

public class Example {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String input;

        System.out.println("输入exit结束程序:");
        while (!(input = scanner.nextLine()).equals("exit")) {
            System.out.println("您输入的内容是: " + input);
        }
        scanner.close();
    }
}
```
在此示例中，程序将持续读取用户输入，并在用户输入"exit"时结束。

## 说明
- **常见陷阱**：务必确保循环条件在某个时刻会变为假。否则，可能会导致无限循环。
- **初始化和更新**：在`while`循环中，确保循环变量在循环体内有适当的更新逻辑，以避免无限循环。
- **使用`break`语句**：可以在循环体中使用`break`语句提前退出循环，但应谨慎使用，以免影响代码的可读性。

## 一句话总结
`while`循环是Java中用于在条件为真时重复执行代码块的基本控制结构。