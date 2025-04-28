<!--
Meta Description: # Java中的「while」迴圈：用法與範例 ## 簡介 「while」迴圈是Java程式語言中的一種控制結構，用於在給定條件為真時重複執行一段程式碼。這使得開發者能夠創建靈活且強大的循環結構，以處理反覆執行的任務。 ## 文件說明 ### 目的 「while」迴圈的主要目的是在一個條件為真時重複...
Meta Keywords: while, scanner, java, count, system
-->

# Java中的「while」迴圈：用法與範例

## 簡介
「while」迴圈是Java程式語言中的一種控制結構，用於在給定條件為真時重複執行一段程式碼。這使得開發者能夠創建靈活且強大的循環結構，以處理反覆執行的任務。

## 文件說明
### 目的
「while」迴圈的主要目的是在一個條件為真時重複執行程式碼區塊，直到該條件變為假為止。這使得「while」迴圈非常適合用於不確定次數的迴圈操作。

### 用法
「while」迴圈的基本語法如下：

```java
while (條件) {
    // 執行的程式碼
}
```

- **條件**：一個布林表達式，當其為真時，迴圈將繼續執行。
- **執行的程式碼**：當條件為真時將被執行的程式碼區塊。

### 詳細說明
在執行「while」迴圈之前，首先會檢查條件。如果條件為真，則執行程式碼區塊，然後再次檢查條件，這個過程會一直重複，直到條件變為假。若條件在第一次檢查時即為假，則程式碼區塊將不會被執行。

## 範例
以下是幾個「while」迴圈的基本使用範例：

### 範例 1：簡單的計數器
```java
int count = 0;
while (count < 5) {
    System.out.println("計數器的值: " + count);
    count++;
}
```

### 範例 2：用戶輸入的迴圈
```java
import java.util.Scanner;

public class UserInput {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String input;
        
        System.out.println("請輸入 'exit' 以結束：");
        while (!(input = scanner.nextLine()).equals("exit")) {
            System.out.println("你輸入的內容是: " + input);
        }
        
        scanner.close();
    }
}
```

## 解釋
### 常見問題
- **無窮迴圈**：如果條件永遠為真，則「while」迴圈會無限執行，這會導致程式崩潰。確保迴圈內有條件改變的程式碼。
- **條件檢查**：在「while」迴圈開始之前進行條件檢查，可能導致程式碼區塊不執行。因此，務必合理設置初始值和條件。

### 注意事項
- 使用「while」迴圈時需謹慎控制條件，確保在某個時刻條件會變為假。
- 了解其他迴圈結構（如「for」迴圈）在特定情況下可能更為適合。

## 一行總結
「while」迴圈是一種控制結構，允許在條件為真時重複執行程式碼，是Java中處理迴圈的基本工具之一。