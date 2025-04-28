<!--
Meta Description: # Java中的finally關鍵字：用於異常處理的終結者 ## 概要 `finally`是Java語言中的一個關鍵字，主要用於異常處理中，確保即使在發生異常的情況下，某些代碼仍然會被執行。它常與`try`和`catch`語句一同使用，形成一個完整的異常處理結構。 ## 文檔 ### 目的 `fin...
Meta Keywords: finally, try, catch, system, out
-->

# Java中的finally關鍵字：用於異常處理的終結者

## 概要
`finally`是Java語言中的一個關鍵字，主要用於異常處理中，確保即使在發生異常的情況下，某些代碼仍然會被執行。它常與`try`和`catch`語句一同使用，形成一個完整的異常處理結構。

## 文檔
### 目的
`finally`塊的主要目的是保證無論`try`塊中的代碼是否成功執行，`finally`塊中的代碼都會被執行。這對於資源釋放（如關閉文件流、釋放數據庫連接等）特別重要。

### 使用方式
在Java中，`finally`塊是可選的，通常與`try`和`catch`語句一同使用。語法如下：

```java
try {
    // 可能會拋出異常的代碼
} catch (ExceptionType e) {
    // 處理異常的代碼
} finally {
    // 總會執行的代碼
}
```

### 詳細說明
- `finally`塊無論異常是否發生都會執行，這在釋放資源、清理操作等場景中非常有用。
- 如果`try`塊中存在`System.exit()`，則`finally`塊將不會被執行。
- `finally`塊可以沒有`catch`塊，但必須有`try`塊。
- 若`try`塊中的代碼執行過程中發生了未處理的異常，`finally`塊仍會執行。

## 範例
以下是使用`finally`的基本示例：

```java
public class FinallyExample {
    public static void main(String[] args) {
        try {
            int[] numbers = {1, 2, 3};
            System.out.println(numbers[3]); // 這將拋出ArrayIndexOutOfBoundsException
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("捕獲到異常: " + e.getMessage());
        } finally {
            System.out.println("這段代碼總是會執行。");
        }
    }
}
```

執行該程式碼後，將輸出：
```
捕獲到異常: Index 3 out of bounds for length 3
這段代碼總是會執行。
```

## 解釋
- **常見陷阱**：在`try`塊中使用`return`語句時，`finally`塊仍然會執行，但這可能會導致一些意想不到的行為，因此需要謹慎處理。
- **注意事項**：如果`finally`塊中拋出異常，則將覆蓋`try`或`catch`塊中的異常。因此，應避免在`finally`中執行可能拋出異常的代碼，或者進行適當的異常處理。

## 一句總結
`finally`關鍵字確保在異常處理過程中，無論發生何種情況，指定的代碼都會被執行。