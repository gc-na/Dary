<!--
Meta Description: # Java 中的 "case" 語法 ## 簡介 在 Java 編程語言中，"case" 是 switch 語句的一部分，用於根據變量的值選擇執行的代碼塊。這種語法讓條件判斷更加簡潔明瞭，尤其是當需要根據一個變量的多個可能值來執行不同的代碼時。 ## 文件說明 "case" 關鍵字的主要用途是與 ...
Meta Keywords: case, break, switch, java, system
-->

# Java 中的 "case" 語法

## 簡介
在 Java 編程語言中，"case" 是 switch 語句的一部分，用於根據變量的值選擇執行的代碼塊。這種語法讓條件判斷更加簡潔明瞭，尤其是當需要根據一個變量的多個可能值來執行不同的代碼時。

## 文件說明
"case" 關鍵字的主要用途是與 switch 語句結合使用，為不同的條件提供不同的執行路徑。這種語法結構可提高代碼的可讀性，並簡化多重條件的判斷。

### 使用方法
在 Java 中，switch 語句的基本結構如下：

```java
switch (expression) {
    case value1:
        // 當 expression 等於 value1 時執行的代碼
        break;
    case value2:
        // 當 expression 等於 value2 時執行的代碼
        break;
    default:
        // 當沒有任何 case 匹配時執行的代碼
}
```

在 switch 語句中，"case" 關鍵字後面跟隨特定的值（如整數、字符串或枚舉），當表達式的值匹配時，將執行對應的代碼塊。每個 case 後面通常會有一個 `break` 語句，這樣可以防止程序繼續執行下一個 case 的代碼。

## 範例
以下是使用 "case" 的基本示例：

```java
int day = 3;
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
    case 5:
        System.out.println("星期五");
        break;
    default:
        System.out.println("週末");
}
```

在這個例子中，當 `day` 的值為 3 時，將輸出 "星期三"。

## 解釋
使用 "case" 時需要注意以下幾點：
- **缺少 break 的情況**：如果在 case 結尾遺漏了 `break`，程式碼將會繼續執行下一個 case 的內容，這被稱為“fall-through”行為，可能導致意想不到的結果。
- **使用 default**：為了處理所有未匹配的情況，可以使用 `default` case，這是一個良好的編程習慣。
- **數據類型**：switch 表達式的數據類型可以是整數、字符、字串或枚舉，但不能是浮點數或 boolean。

## 總結
在 Java 中，"case" 關鍵字用於 switch 語句中，幫助開發者根據變量值選擇不同的代碼路徑，從而提高代碼的可讀性和維護性。