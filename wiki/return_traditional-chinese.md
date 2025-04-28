<!--
Meta Description: # Java 中的「return」關鍵字 ## 概述 在 Java 程式語言中，「return」關鍵字用於從方法中返回值或結束方法的執行。這個功能不僅是方法的結束標誌，也是將計算結果傳遞回調用者的重要機制。 ## 文檔 ### 目的 「return」關鍵字的主要目的是結束方法的執行並返回一個值（如果...
Meta Keywords: return, java, int, void, public
-->

# Java 中的「return」關鍵字

## 概述
在 Java 程式語言中，「return」關鍵字用於從方法中返回值或結束方法的執行。這個功能不僅是方法的結束標誌，也是將計算結果傳遞回調用者的重要機制。

## 文檔
### 目的
「return」關鍵字的主要目的是結束方法的執行並返回一個值（如果方法定義了返回值類型）。這使得方法能夠產生一個結果，並將該結果傳遞給調用該方法的代碼，從而實現數據的流動和處理。

### 用法
在 Java 中，使用「return」關鍵字的基本語法如下：

```java
return [表達式];
```

- 如果方法的返回類型為 `void`，則「return」關鍵字可以單獨使用以結束方法：
  
  ```java
  void myMethod() {
      // 其他程式碼
      return; // 結束方法
  }
  ```

- 如果方法有返回值，則必須在「return」語句後面提供一個與返回類型相符的表達式：

  ```java
  int add(int a, int b) {
      return a + b; // 返回兩個數的和
  }
  ```

### 詳細說明
- **返回類型**：方法的返回類型必須與「return」語句後的表達式類型相匹配。若不匹配，編譯器將報錯。
- **多重返回**：可以在同一方法中使用多個「return」語句，根據不同的條件返回不同的值。
- **方法結束**：當執行到「return」語句時，方法的執行將立即終止，並返回控制權給調用者。

## 範例
以下是關於「return」的基本用法範例：

```java
public class ReturnExample {
    // 一個返回整數的加法方法
    public int add(int a, int b) {
        return a + b; // 返回兩數的和
    }

    // 一個不返回值的方法
    public void printMessage() {
        System.out.println("Hello, World!");
        return; // 可以選擇性地使用
    }

    public static void main(String[] args) {
        ReturnExample example = new ReturnExample();
        int result = example.add(5, 10); // result 現在是 15
        System.out.println("Sum: " + result);
        example.printMessage(); // 打印 "Hello, World!"
    }
}
```

## 解釋
- **常見陷阱**：在方法中使用「return」時，必須確保所有可能的情況都有返回值。否則，編譯器會報錯，提示方法未返回值。
- **返回類型不匹配**：確保「return」後的表達式類型與方法定義的返回類型一致。若不一致，將導致編譯錯誤。
- **未使用的返回值**：在某些情況下，返回的值可能未被使用，這可能會導致無意義的計算。

## 一句總結
「return」關鍵字在 Java 中用於結束方法執行並返回結果，使得方法能夠有效地傳遞數據。