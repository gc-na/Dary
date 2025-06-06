<!--
Meta Description: # Java 中的 for 循环：用法与实例 ## 概述 在 Java 编程语言中，`for` 循环是一种用于重复执行代码块的控制结构。它允许开发者轻松地遍历数组、集合或执行固定次数的循环操作。 ## 文档 `for` 循环的基本语法如下： ```java for (初始化; 条件; 迭代) { /...
Meta Keywords: java, int, system, out, println
-->

# Java 中的 for 循环：用法与实例

## 概述
在 Java 编程语言中，`for` 循环是一种用于重复执行代码块的控制结构。它允许开发者轻松地遍历数组、集合或执行固定次数的循环操作。

## 文档
`for` 循环的基本语法如下：

```java
for (初始化; 条件; 迭代) {
    // 循环体
}
```

### 目的
`for` 循环的主要目的是在满足特定条件的情况下反复执行一段代码。它通常用于需要按顺序访问数组元素或执行特定次数操作的场景。

### 用法
1. **初始化**: 在循环开始前执行的代码，通常用于声明和初始化循环变量。
2. **条件**: 在每次循环开始前评估的布尔表达式。当条件为 `true` 时，执行循环体；当条件为 `false` 时，循环结束。
3. **迭代**: 在每次循环结束后执行的代码，通常用于更新循环变量的值。

### 详细信息
`for` 循环可以与其他控制结构结合使用，支持嵌套循环。它的灵活性使其成为 Java 编程中最常用的循环结构之一。

## 示例
以下是一些基本的 `for` 循环使用示例：

### 示例 1：打印数字
```java
for (int i = 0; i < 5; i++) {
    System.out.println(i);
}
```
该代码将输出数字 0 到 4。

### 示例 2：遍历数组
```java
int[] numbers = {1, 2, 3, 4, 5};
for (int i = 0; i < numbers.length; i++) {
    System.out.println(numbers[i]);
}
```
该代码将遍历并打印数组中的每个元素。

### 示例 3：嵌套循环
```java
for (int i = 0; i < 3; i++) {
    for (int j = 0; j < 2; j++) {
        System.out.println("i = " + i + ", j = " + j);
    }
}
```
该代码将输出 `i` 和 `j` 的所有组合。

## 解释
- **常见陷阱**: 在使用 `for` 循环时，确保循环变量的初始化、条件和迭代部分正确无误。否则可能导致无限循环或数组越界。
- **注意事项**: 在循环中修改循环变量的值可能导致意外行为，建议在迭代部分使用单一的增量或减量操作。

## 一句话总结
`for` 循环是 Java 中用于重复执行代码块的一种强大控制结构，适合遍历数组和执行固定次数的操作。