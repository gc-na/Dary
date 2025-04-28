<!--
Meta Description: # JAVA 中的 "throws" 關鍵字 - 處理異常的有效工具 ## 簡介 在JAVA程式設計中，`throws` 關鍵字用於宣告一個方法可能會拋出異常。這使得調用該方法的代碼能夠更好地處理異常情況，從而提高程式的穩定性和可維護性。 ## 文檔 `throws` 關鍵字的主要目的是告訴程式的使...
Meta Keywords: throws, ioexception, example, java, public
-->

# JAVA 中的 "throws" 關鍵字 - 處理異常的有效工具

## 簡介
在JAVA程式設計中，`throws` 關鍵字用於宣告一個方法可能會拋出異常。這使得調用該方法的代碼能夠更好地處理異常情況，從而提高程式的穩定性和可維護性。

## 文檔
`throws` 關鍵字的主要目的是告訴程式的使用者該方法可能會出現某些異常，這些異常需要在調用該方法時進行處理。使用 `throws` 可以使得異常的處理變得清晰明瞭，也便於代碼的維護。

### 使用方式
在方法的宣告中，`throws` 需要跟隨一個或多個異常類型，這些類型可以是檢查型異常（checked exceptions）或運行時異常（unchecked exceptions）。例如：

```java
public void myMethod() throws IOException {
    // 方法內容
}
```

在這個例子中，`myMethod` 可能會拋出 `IOException`，調用者必須處理這個異常。

### 詳細說明
- **檢查型異常 vs. 運行時異常**: 只有檢查型異常需要在方法簽名中使用 `throws` 宣告，運行時異常則不需要。
- **多個異常**: 可以用逗號分隔多個異常類型，例如：`throws IOException, SQLException`。
- **異常鏈**: 當一個方法拋出異常，並且該異常在另一個方法中被捕獲並重新拋出時，可以使用 `throws` 來將異常傳遞給上層調用。

## 範例
以下是使用 `throws` 的基本範例：

```java
import java.io.*;

public class Example {
    public void readFile(String filename) throws IOException {
        FileReader file = new FileReader(filename);
        BufferedReader br = new BufferedReader(file);
        String line;
        while ((line = br.readLine()) != null) {
            System.out.println(line);
        }
        br.close();
    }
    
    public static void main(String[] args) {
        Example example = new Example();
        try {
            example.readFile("test.txt");
        } catch (IOException e) {
            System.out.println("發生異常: " + e.getMessage());
        }
    }
}
```

在這個範例中，`readFile` 方法宣告了會拋出 `IOException`，而在 `main` 方法中使用 `try-catch` 來處理這個異常。

## 解釋
- **常見陷阱**: 忘記在方法中處理可能的異常，這會導致編譯錯誤。確保對所有檢查型異常進行處理。
- **不必要的使用**: 對於運行時異常，不需要使用 `throws` 來聲明，因為它們不需要強制捕獲。
- **清晰的異常處理**: 使用 `throws` 可以提高代碼的可讀性，讓調用者清楚了解需要處理哪些異常。

## 一句總結
`throws` 關鍵字在JAVA中用於宣告方法可能拋出的異常，幫助開發者進行有效的異常處理。