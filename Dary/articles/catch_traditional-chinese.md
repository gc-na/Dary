<!--
Meta Description: # Java 中的 catch：處理異常的關鍵字 ## 簡介 在 Java 程式設計中，`catch` 是一個用於處理異常的關鍵字。它通常與 `try` 區塊結合使用，以捕獲和處理運行時發生的錯誤，從而提高程式的穩定性和可預測性。 ## 文檔 ### 目的 `catch` 的主要目的是捕捉在 `tr...
Meta Keywords: catch, java, try, public, system
-->

# Java 中的 catch：處理異常的關鍵字

## 簡介
在 Java 程式設計中，`catch` 是一個用於處理異常的關鍵字。它通常與 `try` 區塊結合使用，以捕獲和處理運行時發生的錯誤，從而提高程式的穩定性和可預測性。

## 文檔
### 目的
`catch` 的主要目的是捕捉在 `try` 區塊中可能發生的異常，並執行相應的錯誤處理邏輯。

### 使用方式
在 Java 中，`catch` 用於捕獲特定類型的異常，語法結構如下：

```java
try {
    // 可能會拋出異常的代碼
} catch (ExceptionType e) {
    // 處理異常的代碼
}
```

- `try` 區塊包含可能會引發異常的程式碼。
- `catch` 區塊則用來處理由 `try` 區塊拋出的異常。
- `ExceptionType` 是要捕獲的異常類型，可以是 Java 標準異常類型（如 `NullPointerException`、`IOException` 等），也可以是自定義的異常類型。

### 詳細信息
- 可以有多個 `catch` 區塊，用於捕獲不同類型的異常。
- `catch` 區塊中的變數（例如上面的 `e`）可以用來訪問異常的詳細信息，例如錯誤消息和堆棧跟蹤。
- `catch` 區塊可以有一個可選的 `finally` 區塊，無論是否發生異常，`finally` 區塊中的代碼都會執行。

## 範例
### 基本使用範例
以下是一個簡單的示例，展示如何使用 `catch` 處理異常：

```java
public class CatchExample {
    public static void main(String[] args) {
        try {
            int result = 10 / 0; // 這裡會產生 ArithmeticException
        } catch (ArithmeticException e) {
            System.out.println("發生了算術異常：" + e.getMessage());
        }
    }
}
```

### 多個 catch 範例
```java
public class MultiCatchExample {
    public static void main(String[] args) {
        try {
            String str = null;
            System.out.println(str.length()); // 這裡會產生 NullPointerException
        } catch (NullPointerException e) {
            System.out.println("發生了空指針異常：" + e.getMessage());
        } catch (Exception e) {
            System.out.println("發生了一般異常：" + e.getMessage());
        }
    }
}
```

## 解釋
### 常見問題
- **未捕獲的異常**：如果異常未被 `catch` 捕獲，程式將終止並顯示錯誤信息。
- **多重捕獲**：當使用多個 `catch` 區塊時，最具體的異常類型應該放在前面，否則會導致編譯錯誤。
- **使用自定義異常**：可以通過擴展 `Exception` 類來創建自定義異常，並在 `catch` 中捕獲這些自定義異常。

## 一句話總結
`catch` 是 Java 中用於捕獲和處理異常的關鍵字，能有效提高程式的穩定性和錯誤處理能力。