<!--
Meta Description: # Java 中的 "new" 關鍵字：物件創建的關鍵 ## 簡介 在 Java 編程中，"new" 關鍵字是用於創建對象的基本命令。它不僅用來實例化類別，還涉及到內存分配和對象初始化的過程。 ## 文檔 ### 目的 "new" 關鍵字的主要目的是在 Java 中創建新的對象實例。當使用 "new...
Meta Keywords: new, java, name, dog, classname
-->

# Java 中的 "new" 關鍵字：物件創建的關鍵

## 簡介
在 Java 編程中，"new" 關鍵字是用於創建對象的基本命令。它不僅用來實例化類別，還涉及到內存分配和對象初始化的過程。

## 文檔
### 目的
"new" 關鍵字的主要目的是在 Java 中創建新的對象實例。當使用 "new" 時，Java 會在堆內存中分配適當的空間，並調用相應的建構子來初始化對象。

### 用法
在 Java 中，"new" 關鍵字通常用於以下語法：
```java
ClassName objectName = new ClassName();
```
這行代碼會創建 `ClassName` 類的一個新實例，並將其分配給變量 `objectName`。

### 詳細說明
- **內存分配**：當使用 "new" 創建一個對象時，Java 會在堆內存中分配內存。
- **對象初始化**：隨後，Java 會調用相應的建構子來初始化該對象。
- **返回引用**：`new` 關鍵字返回對新創建對象的引用，這意味著你可以通過這個引用來訪問對象的方法和屬性。

## 範例
### 基本用法示例
```java
// 定義一個類
class Dog {
    String name;

    Dog(String name) {
        this.name = name;
    }

    void bark() {
        System.out.println(name + " says woof!");
    }
}

// 使用 "new" 創建對象
public class Main {
    public static void main(String[] args) {
        Dog myDog = new Dog("Buddy");
        myDog.bark(); // 輸出：Buddy says woof!
    }
}
```

## 解釋
### 常見陷阱
- **未初始化的對象**：如果在創建對象時未使用 "new"，將會導致 `NullPointerException`，因為變量將仍然是 `null`。
- **自定義建構子**：如果類中定義了自定義建構子而沒有提供默認的無參建構子，則不可以使用無參構造創建對象。

### 注意事項
- 使用 "new" 會導致內存開銷，應注意對象的生命周期以及何時釋放內存。
- Java 的垃圾回收機制會自動釋放不再使用的對象，但在高性能應用中，對象的創建和銷毀仍需謹慎控制。

## 一句話總結
在 Java 中，"new" 關鍵字用於創建對象實例，並在堆內存中進行相應的初始化。