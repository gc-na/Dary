<!--
Meta Description: # Java 中的 Switch 語句：用於多重選擇的高效工具 ## 概述 在 Java 編程語言中，`switch` 語句是一種控制流語句，允許根據變量的值選擇執行不同的代碼路徑。它通常用於取代多重的 `if-else` 條件判斷，使代碼更加清晰和可讀。 ## 文檔 ### 目的 `switch`...
Meta Keywords: case, switch, break, dayname, java
-->

# Java 中的 Switch 語句：用於多重選擇的高效工具

## 概述
在 Java 編程語言中，`switch` 語句是一種控制流語句，允許根據變量的值選擇執行不同的代碼路徑。它通常用於取代多重的 `if-else` 條件判斷，使代碼更加清晰和可讀。

## 文檔
### 目的
`switch` 語句的主要目的是簡化多重條件的判斷，特別是當需要根據一個變量的多個可能值執行不同代碼時。

### 用法
語法結構如下：
```java
switch (expression) {
    case value1:
        // 執行代碼
        break;
    case value2:
        // 執行代碼
        break;
    // 可以有多個 case
    default:
        // 執行代碼
}
```
- `expression` 必須是 `int`、`byte`、`short`、`char`、`String` 或其包裝類型。
- 每個 `case` 後跟一個可能的值，當 `expression` 的值與 `case` 的值匹配時，將執行相應的代碼。
- `break` 語句用於終止 `switch` 塊。如果省略，將繼續執行下一個 `case` 的代碼，這稱為「fall-through」。

### 詳細說明
- `default` 是可選的，當沒有 `case` 匹配時執行。
- `switch` 語句可以提高代碼可讀性，尤其是當有多個可能的選擇時。
- 在 Java 12 及更高版本中，`switch` 語句還支持改進的語法，允許使用表達式來返回值。

## 範例
### 基本用法示例
以下是使用 `switch` 語句的簡單範例：
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
        dayName = "無效的日期";
}

System.out.println(dayName); // 輸出：星期三
```

## 解釋
### 常見陷阱
- 忘記 `break` 語句會導致意外的 `fall-through` 行為，可能會執行多個 `case` 的代碼。
- `switch` 不支持 `long` 和 `float` 類型，但從 Java 7 開始支持 `String` 類型。
- 請注意，使用 `case` 字串時，區分大小寫。

### 附加說明
在 Java 12 及以後的版本中，可以使用 `switch` 表達式來簡化代碼，例如：
```java
String dayName = switch (day) {
    case 1 -> "星期一";
    case 2 -> "星期二";
    case 3 -> "星期三";
    case 4 -> "星期四";
    case 5 -> "星期五";
    case 6 -> "星期六";
    case 7 -> "星期日";
    default -> "無效的日期";
};
```
這樣的寫法更簡潔並且可讀性更高。

## 一行總結
Java 中的 `switch` 語句是一個高效的控制流工具，用於根據變量的值選擇執行不同的代碼路徑。