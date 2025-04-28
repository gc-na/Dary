<!--
Meta Description: # JAVA 中的 "while" 循環指令詳解 ## 概要 "while" 是 JAVA 編程語言中的一個控制結構，允許在特定條件滿足時反覆執行一段代碼。它通常用於需要重複執行某些操作的場景，直到條件不再為真。 ## 文件說明 "while" 循環的基本語法如下： ```java while (條...
Meta Keywords: while, java, scanner, public, system
-->

# JAVA 中的 "while" 循環指令詳解

## 概要
"while" 是 JAVA 編程語言中的一個控制結構，允許在特定條件滿足時反覆執行一段代碼。它通常用於需要重複執行某些操作的場景，直到條件不再為真。

## 文件說明
"while" 循環的基本語法如下：

```java
while (條件) {
    // 執行的代碼
}
```

### 目的
"while" 循環的主要目的是在條件為真時持續執行代碼區塊，這在處理不確定次數的迴圈時特別有用。

### 用法
1. **條件評估**：在每次迴圈開始之前，首先評估括號內的條件。如果條件為真，則執行代碼區塊；如果為假，則退出循環。
2. **無限循環**：需要小心處理，因為如果條件永遠為真，則會導致無限循環。
3. **循環控制**：可以使用 `break` 和 `continue` 語句來控制循環的執行流程。

## 範例
### 基本用法範例
以下是 "while" 循環的簡單範例，顯示如何計算從 1 到 5 的總和：

```java
public class WhileExample {
    public static void main(String[] args) {
        int sum = 0;
        int i = 1;

        while (i <= 5) {
            sum += i;
            i++;
        }

        System.out.println("總和是: " + sum); // 輸出: 總和是: 15
    }
}
```

### 使用者輸入範例
下面的範例顯示如何使用 "while" 循環來接收使用者的輸入，直到輸入 "exit" 為止：

```java
import java.util.Scanner;

public class WhileInputExample {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String input;

        System.out.println("請輸入文字 (輸入 'exit' 退出):");

        while (true) {
            input = scanner.nextLine();
            if (input.equals("exit")) {
                break;
            }
            System.out.println("你輸入的文字是: " + input);
        }

        scanner.close();
    }
}
```

## 解釋
### 常見陷阱
1. **無限循環**：未正確更新條件變數，會導致無限循環。例如，在上面的範例中，如果不增加 `i`，則條件 `i <= 5` 始終為真。
2. **條件評估錯誤**：確保條件的邏輯正確，否則可能會導致意外行為。
3. **使用 `break` 和 `continue`**：這兩個語句能有效控制循環，但過度使用可能會使代碼難以閱讀。

### 附加說明
在編寫循環時，建議保持代碼的可讀性，並在需要時添加註解，幫助未來的維護。

## 一句總結
"while" 循環在 JAVA 中是一種控制結構，允許在條件為真時重複執行指定的代碼區塊。