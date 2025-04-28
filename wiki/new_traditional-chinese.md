<!--
Meta Description: # Java 中的 "new" 關鍵字：對象創建的基礎 ## 概述 在 Java 程式設計中，`new` 是一個關鍵字，用於創建對象的實例。它是面向對象編程的核心，允許開發者在執行時動態分配內存並初始化對象。 ## 文檔 `new` 關鍵字的主要目的是創建類的實例。當使用 `new` 關鍵字時，Ja...
Meta Keywords: new, java, public, name, classname
-->

# Java 中的 "new" 關鍵字：對象創建的基礎

## 概述
在 Java 程式設計中，`new` 是一個關鍵字，用於創建對象的實例。它是面向對象編程的核心，允許開發者在執行時動態分配內存並初始化對象。

## 文檔
`new` 關鍵字的主要目的是創建類的實例。當使用 `new` 關鍵字時，Java 虛擬機（JVM）會執行以下步驟：
1. 分配內存：為新對象分配必要的內存。
2. 初始化對象：調用類的構造函數來初始化對象的狀態。
3. 返回對象引用：返回指向新創建對象的引用。

### 用法
`new` 關鍵字的基本語法如下：
```java
ClassName objectReference = new ClassName();
```
這裡，`ClassName` 是要創建的類的名稱，`objectReference` 是對象的引用變量。

### 詳細資訊
- 可以使用 `new` 關鍵字創建任何類的實例，包括內部類、數組等。
- 如果類有參數化的構造函數，則可以使用 `new` 關鍵字並提供相應的參數：
  ```java
  ClassName objectReference = new ClassName(parameter1, parameter2);
  ```
- 對於數組，可以使用：
  ```java
  DataType[] arrayReference = new DataType[arraySize];
  ```

## 範例
以下是一些使用 `new` 關鍵字的基本範例：

### 範例 1: 創建單一對象
```java
public class Dog {
    String name;

    public Dog(String name) {
        this.name = name;
    }
}

public class Main {
    public static void main(String[] args) {
        Dog myDog = new Dog("Buddy");
        System.out.println("Dog's name: " + myDog.name);
    }
}
```

### 範例 2: 創建數組
```java
public class Main {
    public static void main(String[] args) {
        int[] numbers = new int[5];
        for (int i = 0; i < numbers.length; i++) {
            numbers[i] = i * 10;
        }
        for (int number : numbers) {
            System.out.println(number);
        }
    }
}
```

## 解釋
在使用 `new` 關鍵字時，開發者可能會遇到一些常見的陷阱和注意事項：
- **NullPointerException**：如果未正確初始化對象引用，將導致 NullPointerException。確保在使用對象之前已經使用 `new` 創建了它。
- **內存泄露**：在某些情況下，如果對象不再需要但仍然持有引用，則可能會導致內存泄露。使用完對象後，及時將其引用設置為 `null` 是一個好習慣。
- **構造函數的重載**：當類中有多個構造函數時，確保傳遞正確的參數，以避免編譯錯誤或運行時異常。

## 總結
`new` 關鍵字是 Java 中創建對象的基本工具，使開發者能夠動態分配內存並初始化對象。