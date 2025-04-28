<!--
Meta Description: # Java中的import語句：簡介與詳細使用指南 ## 概述 在Java編程語言中，`import`語句用於導入其他包中的類和接口，從而使其可以在當前Java文件中使用。這個特性使得代碼更加模組化，並提高了代碼的可讀性和可維護性。 ## 文檔 ### 目的 `import`語句的主要目的是讓開發...
Meta Keywords: import, java, static, public, list
-->

# Java中的import語句：簡介與詳細使用指南

## 概述
在Java編程語言中，`import`語句用於導入其他包中的類和接口，從而使其可以在當前Java文件中使用。這個特性使得代碼更加模組化，並提高了代碼的可讀性和可維護性。

## 文檔
### 目的
`import`語句的主要目的是讓開發者可以輕鬆使用其他包中的類和接口，而無需使用完整的包名。這樣可以減少代碼的冗長性，提高開發效率。

### 使用
在Java中，`import`語句通常放在Java文件的頂部，類定義之前。語法結構如下：
```java
import package_name.class_name;
```
或者可以使用星號（*）導入整個包：
```java
import package_name.*;
```

### 詳細信息
- **包的概念**：Java中的包是一組相關類和接口的集合。使用包可以組織代碼，避免命名衝突。
- **靜態導入**：Java還支持靜態導入，允許開發者導入類中的靜態成員，這樣可以直接使用靜態方法和變量，而無需類名。例如：
```java
import static package_name.ClassName.staticMember;
```
- **導入的範圍**：`import`語句只在當前Java文件中有效，並不影響其他文件。

## 範例
```java
// 導入java.util包中的ArrayList類
import java.util.ArrayList;

public class Example {
    public static void main(String[] args) {
        // 使用ArrayList類
        ArrayList<String> list = new ArrayList<>();
        list.add("Hello");
        list.add("World");
        System.out.println(list);
    }
}
```

```java
// 靜態導入java.lang.Math類中的PI常量
import static java.lang.Math.PI;

public class Circle {
    public static void main(String[] args) {
        double radius = 5;
        double area = PI * radius * radius;
        System.out.println("Area of the circle: " + area);
    }
}
```

## 解釋
- **常見陷阱**：開發者在使用`import`語句時，應注意避免導入不必要的包，因為這會增加編譯時間和導入的複雜性。
- **命名衝突**：如果兩個導入的包中有相同的類名，則需要使用完整的包名來區分。這通常會導致代碼可讀性下降。
- **不需要的導入**：如果導入了未使用的類，編譯器會給出警告，因此建議定期檢查和清理不必要的導入。

## 總結
Java中的`import`語句是用於導入其他包中的類和接口的工具，它簡化了代碼並提高了可讀性。