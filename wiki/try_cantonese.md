<!--
Meta Description: # JAVA 的 "try" 語句：異常處理的基礎 ## 概要 在 JAVA 程式設計中，`try` 語句用於捕獲和處理異常，確保程式在遇到錯誤時不會中止，從而提高程式的穩定性和可靠性。 ## 文檔 `try` 語句的主要目的是為了捕獲可能在程式執行過程中發生的異常，並提供相應的處理機制。當在 `t...
Meta Keywords: try, java, catch, finally, arithmeticexception
-->

# JAVA 的 "try" 語句：異常處理的基礎

## 概要
在 JAVA 程式設計中，`try` 語句用於捕獲和處理異常，確保程式在遇到錯誤時不會中止，從而提高程式的穩定性和可靠性。

## 文檔
`try` 語句的主要目的是為了捕獲可能在程式執行過程中發生的異常，並提供相應的處理機制。當在 `try` 區塊中執行的代碼發生異常時，控制權會轉移到對應的 `catch` 區塊，這樣開發者可以根據異常類型進行特定的錯誤處理。

### 語法
```java
try {
    // 可能發生異常的代碼
} catch (ExceptionType e) {
    // 異常處理代碼
} finally {
    // 可選的清理代碼
}
```

### 用法
1. **捕獲異常**：在 `try` 區塊中包裹可能拋出異常的代碼。
2. **處理異常**：在 `catch` 區塊中處理特定的異常。
3. **清理資源**：`finally` 區塊中的代碼無論是否捕獲到異常都會執行，通常用來釋放資源。

## 範例
### 基本用法
```java
public class TryExample {
    public static void main(String[] args) {
        try {
            int result = 10 / 0; // 這裡會拋出 ArithmeticException
        } catch (ArithmeticException e) {
            System.out.println("發生了數學異常: " + e.getMessage());
        } finally {
            System.out.println("這行代碼會始終執行。");
        }
    }
}
```
在這個例子中，程式會捕獲到 `ArithmeticException` 並打印相應的錯誤消息。

## 解釋
- **常見陷阱**：未捕獲的異常會導致程式崩潰，因此務必確保對重要的代碼進行異常處理。
- **多個 catch 區塊**：可以為同一個 `try` 區塊使用多個 `catch` 區塊，以處理不同類型的異常。
- **自定義異常**：除了 Java 提供的異常類型，開發者還可以創建自定義異常類型以應對特定情況。

## 一句總結
`try` 語句是 JAVA 中異常處理的核心工具，幫助開發者捕獲和處理程式執行中的錯誤。