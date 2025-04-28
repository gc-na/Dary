<!--
Meta Description: # Java 中的 case 語句詳解 ## 簡介 在 Java 程式語言中，`case` 語句是 `switch` 語句的一部分，用於根據變數的值執行不同的程式區塊。它提供了一種簡潔的方式來處理多個條件，通常用於取代多個 `if-else` 語句。 ## 文檔 ### 目的 `case` 語句的主...
Meta Keywords: case, break, switch, java, system
-->

# Java 中的 case 語句詳解

## 簡介
在 Java 程式語言中，`case` 語句是 `switch` 語句的一部分，用於根據變數的值執行不同的程式區塊。它提供了一種簡潔的方式來處理多個條件，通常用於取代多個 `if-else` 語句。

## 文檔
### 目的
`case` 語句的主要目的是在給定的 `switch` 語句中，根據變數的特定值選擇要執行的程式碼區塊。這使得程式碼更加清晰和可讀，特別是在需要處理多個可能值的情況下。

### 用法
`case` 語句通常與 `switch` 語句一起使用。基本語法如下：

```java
switch (expression) {
    case value1:
        // 執行的程式碼
        break;
    case value2:
        // 執行的程式碼
        break;
    // 可以有多個 case
    default:
        // 如果沒有匹配到任何 case，執行的程式碼
}
```

- **expression**：要檢查的變數或表達式，必須是 `int`、`char`、`String` 等可被評估的類型。
- **case value**：每個 `case` 定義一個可能的值，如果 `expression` 與這個值匹配，則執行對應的程式碼。
- **break**：用於退出 `switch` 語句，避免執行後續的 `case`。如果省略 `break`，將會發生「fall-through」，即執行匹配後的所有 `case`。

### 詳細說明
`case` 語句的主要特點包括：
- 支援多種數據類型（包括整數、字符和字串）。
- 允許使用 `default` case，當沒有其他 `case` 匹配時執行。
- 可在同一個 `case` 中指定多個值，使用逗號分隔。例如：

```java
switch (day) {
    case 1:
    case 2:
    case 3:
        System.out.println("工作日");
        break;
    case 6:
    case 7:
        System.out.println("週末");
        break;
    default:
        System.out.println("無效的日子");
}
```

## 範例
以下是一個簡單的使用範例：

```java
int day = 3;
switch (day) {
    case 1:
        System.out.println("星期一");
        break;
    case 2:
        System.out.println("星期二");
        break;
    case 3:
        System.out.println("星期三");
        break;
    default:
        System.out.println("未知的日子");
}
```

執行上述程式碼，將輸出：`星期三`

## 解釋
在使用 `case` 語句時，開發者應注意以下幾點：
- 忘記使用 `break` 將導致意外的「fall-through」，可能導致不必要的程式碼執行。
- `case` 必須是常量（不可以是變數或表達式）。
- 對於 `String` 類型的 `case`，Java 會進行值的比較，並不會考慮大小寫。

## 一句總結
`case` 語句是 Java 中 `switch` 語句的組成部分，用於根據變數的值執行不同的程式碼區塊，使程式碼更加簡潔易讀。