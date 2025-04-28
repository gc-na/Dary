<!--
Meta Description: # Java 中的 "break" 语句：用法與範例 ## 概述 在 Java 程式設計中，`break` 是一個重要的控制流程語句，用於提前跳出迴圈或 switch 陳述。它可以有效地終止執行某段代碼，幫助開發者更靈活地控制程式流程。 ## 文件說明 ### 目的 `break` 語句的主要目的在...
Meta Keywords: break, switch, case, java, system
-->

# Java 中的 "break" 语句：用法與範例

## 概述
在 Java 程式設計中，`break` 是一個重要的控制流程語句，用於提前跳出迴圈或 switch 陳述。它可以有效地終止執行某段代碼，幫助開發者更靈活地控制程式流程。

## 文件說明
### 目的
`break` 語句的主要目的在於結束當前的迴圈（如 `for`、`while`、或 `do-while`）或 `switch` 陳述。這使得開發者可以在特定條件達成時，立即退出循環或選擇結構。

### 使用方法
`break` 語句的基本語法如下：
```java
break;
```
在 `switch` 陳述中，`break` 通常用於結束一個 case 的執行，避免執行到後續的 case。示例如下：
```java
switch (expression) {
    case value1:
        // 執行的代碼
        break; // 結束switch
    case value2:
        // 執行的代碼
        break; // 結束switch
    default:
        // 執行的代碼
}
```

### 詳細說明
`break` 可用於：
1. **迴圈結束**：在迴圈中，當滿足特定條件時，使用 `break` 可以立即跳出迴圈。
2. **switch 結構**：在 `switch` 陳述中，`break` 用於防止程式執行到下一個 case 的代碼。

## 範例
### 迴圈中使用 `break`
```java
for (int i = 0; i < 10; i++) {
    if (i == 5) {
        break; // 當 i 等於 5 時，跳出迴圈
    }
    System.out.println(i); // 輸出 0 到 4
}
```

### 在 `switch` 中使用 `break`
```java
int day = 4;
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
    case 4:
        System.out.println("星期四");
        break;
    default:
        System.out.println("未知的日子");
}
```

## 解釋
- **常見陷阱**：在 `switch` 中，如果忘記使用 `break`，將導致「穿透」現象，即程式會繼續執行下一個 case 的代碼，這可能會導致意料之外的行為。
- **嵌套迴圈**：使用 `break` 時需注意，如果在嵌套迴圈中使用，僅會跳出當前的迴圈，而不會影響外層迴圈。

## 一句總結
`break` 語句在 Java 中用於提前終止迴圈或 `switch` 陳述，增強了程式的控制流靈活性。