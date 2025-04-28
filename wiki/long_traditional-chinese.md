<!--
Meta Description: # JAVA 中的 long 數據類型詳解 ## 簡介 在 JAVA 編程語言中，`long` 是一種基本數據類型，用於表示64位的整數。它能夠儲存比 `int` 類型更大的整數值，適合存儲需要更高精度的計算結果。 ## 文件說明 `long` 類型的範圍從 -9,223,372,036,854,7...
Meta Keywords: long, java, public, int, system
-->

# JAVA 中的 long 數據類型詳解

## 簡介
在 JAVA 編程語言中，`long` 是一種基本數據類型，用於表示64位的整數。它能夠儲存比 `int` 類型更大的整數值，適合存儲需要更高精度的計算結果。

## 文件說明
`long` 類型的範圍從 -9,223,372,036,854,775,808 到 9,223,372,036,854,775,807。它的主要用途是在需要處理大數據或時間戳時，能夠確保不會因為數值超出範圍而導致溢出。使用 `long` 類型的變量時，必須在數字後加上字母 `L` 或 `l` 來明確指定其為長整數，雖然使用大寫的 `L` 更為推薦，以避免與數字 `1` 混淆。

### 主要用途：
- 儲存大整數
- 處理高精度的計算
- 表示時間（如毫秒）

## 示例
### 基本用法
```java
public class LongExample {
    public static void main(String[] args) {
        long largeNumber = 12345678901234L;
        System.out.println("The large number is: " + largeNumber);
    }
}
```

### 數學運算
```java
public class LongMath {
    public static void main(String[] args) {
        long a = 100000L;
        long b = 200000L;
        long sum = a + b;
        System.out.println("Sum: " + sum);
    }
}
```

### 時間戳示例
```java
public class TimestampExample {
    public static void main(String[] args) {
        long currentTimeMillis = System.currentTimeMillis();
        System.out.println("Current Time in milliseconds: " + currentTimeMillis);
    }
}
```

## 解釋
在使用 `long` 類型時，開發者需注意以下幾點：
- 儲存時必須加上 `L` 來明確告知 JVM 此數據為 `long` 類型，否則會默認為 `int` 類型，可能導致溢出錯誤。
- 當進行數學運算時，若運算涉及 `int` 類型，結果會自動提升為 `int`，可能會引發意外的數據損失。建議在運算中使用 `long` 類型的變量進行計算。
- 在需要與其他數據類型（如 `double`）進行相互轉換時，應謹慎處理，以避免精度損失。

## 總結
`long` 是 JAVA 中用於表示64位整數的基本數據類型，適合需要高精度的計算和大數據的處理。