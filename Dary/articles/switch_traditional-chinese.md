<!--
Meta Description: # JAVA 中的 switch 語句：用於條件判斷的高效工具 ## 簡介 在 JAVA 中，`switch` 語句是一種控制結構，允許根據變量的值執行不同的代碼塊。它是一個高效的選擇語句，特別適合處理多個條件判斷。 ## 文檔 ### 目的 `switch` 語句的主要目的是通過比較一個變量的值來...
Meta Keywords: case, switch, break, dayname, java
-->

# JAVA 中的 switch 語句：用於條件判斷的高效工具

## 簡介
在 JAVA 中，`switch` 語句是一種控制結構，允許根據變量的值執行不同的代碼塊。它是一個高效的選擇語句，特別適合處理多個條件判斷。

## 文檔
### 目的
`switch` 語句的主要目的是通過比較一個變量的值來選擇執行的代碼塊。與長串的 `if-else` 語句相比，`switch` 提供了一種更清晰和易讀的方式來進行多條件判斷。

### 使用方法
`switch` 語句的基本語法如下：

```java
switch (expression) {
    case value1:
        // 當 expression 等於 value1 時執行的代碼
        break;
    case value2:
        // 當 expression 等於 value2 時執行的代碼
        break;
    // 可以有任意數量的 case
    default:
        // 當沒有任何 case 匹配時執行的代碼
}
```

- `expression`：需要進行比較的變量，必須是 `byte`、`short`、`int`、`char`、`String` 或其封裝類型。
- `case`：每個 `case` 標識符後面跟一個常量值，當 `expression` 等於該值時，將執行對應的代碼塊。
- `break`：用於終止 `switch` 語句，防止執行後續的 `case` 代碼。
- `default`：可選項，當沒有匹配的 `case` 時，執行的代碼塊。

## 範例
基本的 `switch` 使用範例：

```java
int day = 3;
String dayName;

switch (day) {
    case 1:
        dayName = "星期一";
        break;
    case 2:
        dayName = "星期二";
        break;
    case 3:
        dayName = "星期三";
        break;
    case 4:
        dayName = "星期四";
        break;
    case 5:
        dayName = "星期五";
        break;
    case 6:
        dayName = "星期六";
        break;
    case 7:
        dayName = "星期日";
        break;
    default:
        dayName = "無效的天數";
}

System.out.println("今天是：" + dayName);
```

另一個使用 `String` 的範例：

```java
String fruit = "apple";

switch (fruit) {
    case "banana":
        System.out.println("這是一根香蕉");
        break;
    case "apple":
        System.out.println("這是一個蘋果");
        break;
    case "orange":
        System.out.println("這是一個橘子");
        break;
    default:
        System.out.println("這是一個未知的水果");
}
```

## 解釋
在使用 `switch` 語句時，有幾個常見的陷阱和注意事項：

1. **缺少 break**：如果在某個 `case` 後缺少 `break`，將導致「fall-through」現象，這意味著後續的 `case` 代碼也會被執行，直到遇到 `break` 或結束 `switch` 。
   
2. **資料類型限制**：`switch` 語句僅支持特定的資料類型（整數、字符、字串等），使用不支持的資料類型會導致編譯錯誤。

3. **不支持範圍判斷**：`switch` 語句無法處理範圍條件，若需要範圍判斷，應使用 `if-else` 語句。

4. **String 的使用**：從 JAVA 7 開始，`switch` 語句支持 `String` 資料型別，使得條件判斷更加靈活。

## 一行總結
`switch` 語句是 JAVA 中一種高效且易讀的多條件判斷工具，適合用於根據變量的值執行不同代碼塊。