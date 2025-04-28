<!--
Meta Description: # Java 中的 break 語句詳細介紹 ## 簡介 在 Java 編程中，`break` 語句用於提前終止循環或 switch 結構，提供了對控制流程的靈活性。 ## 文檔 ### 目的 `break` 語句主要用於終止當前的循環（如 `for`、`while`、`do-while`）或 `s...
Meta Keywords: break, switch, java, system, out
-->

# Java 中的 break 語句詳細介紹

## 簡介
在 Java 編程中，`break` 語句用於提前終止循環或 switch 結構，提供了對控制流程的靈活性。

## 文檔
### 目的
`break` 語句主要用於終止當前的循環（如 `for`、`while`、`do-while`）或 `switch` 語句，讓程序能夠在滿足特定條件時跳出結構，進入下一條語句。

### 用法
`break` 的使用相對簡單，通常放置在條件語句內，當條件成立時執行 `break`，從而退出循環或 `switch`。以下是基本語法：

```java
break; // 用於終止當前循環或switch
```

### 詳細說明
- **在循環中使用**：當在 `for`、`while` 或 `do-while` 循環中使用 `break` 時，程序會立即跳出該循環。
- **在 switch 中使用**：在 `switch` 語句中，`break` 用於防止程式從一個 case 繼續執行到下一個 case。

## 範例
### 基本使用範例
1. **在循環中使用 break**：
   ```java
   public class BreakExample {
       public static void main(String[] args) {
           for (int i = 0; i < 10; i++) {
               if (i == 5) {
                   break; // 當 i 等於 5 時，終止循環
               }
               System.out.println(i);
           }
       }
   }
   ```
   輸出為：
   ```
   0
   1
   2
   3
   4
   ```

2. **在 switch 中使用 break**：
   ```java
   public class SwitchBreakExample {
       public static void main(String[] args) {
           int day = 3;
           switch (day) {
               case 1:
                   System.out.println("星期一");
                   break; // 結束 switch
               case 2:
                   System.out.println("星期二");
                   break; // 結束 switch
               case 3:
                   System.out.println("星期三");
                   break; // 結束 switch
               default:
                   System.out.println("無效的日子");
           }
       }
   }
   ```
   輸出為：
   ```
   星期三
   ```

## 解釋
- **常見問題**：在多層嵌套的循環中，`break` 只會終止最內層的循環。如果需要結束外層循環，可以使用標籤（label）來指定要終止的循環。
- **使用標籤的範例**：
   ```java
   outerLoop:
   for (int i = 0; i < 3; i++) {
       for (int j = 0; j < 3; j++) {
           if (i == 1 && j == 1) {
               break outerLoop; // 終止外層循環
           }
           System.out.println("i = " + i + ", j = " + j);
       }
   }
   ```

## 總結
`break` 語句是 Java 中控制流程的重要工具，可以有效地終止循環或 switch 結構，提升代碼的可讀性與效率。