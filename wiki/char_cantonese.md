<!--
Meta Description: # Java 中的 char: 字符類型的詳細指南 ## 概述 在 Java 編程語言中，`char` 是一種用於表示單一字符的基本數據類型，通常用於處理字元和字符串的操作。 ## 文檔 ### 目的 `char` 類型用來儲存單一的 16 位 Unicode 字符。這使得它能夠表示世界上幾乎所有的...
Meta Keywords: char, java, unicode, system, out
-->

# Java 中的 char: 字符類型的詳細指南

## 概述
在 Java 編程語言中，`char` 是一種用於表示單一字符的基本數據類型，通常用於處理字元和字符串的操作。

## 文檔
### 目的
`char` 類型用來儲存單一的 16 位 Unicode 字符。這使得它能夠表示世界上幾乎所有的字符，包括字母、數字、標點符號及特殊字符。

### 使用方法
在 Java 中，`char` 可以通過直接賦值或使用 Unicode 編碼來初始化。使用單引號來包裹字符，例如：
```java
char letter = 'A';
char number = '1';
char specialChar = '@';
```
如果需要使用 Unicode 編碼，可以使用 `\u` 後接 4 位十六進制數字，例如：
```java
char unicodeChar = '\u0041'; // 代表 'A'
```

### 詳細說明
- `char` 類型佔用 2 個字節的內存，因為 Java 的 `char` 使用 UTF-16 編碼。
- `char` 可以與整數進行運算，因為每個字符都有對應的整數值（ASCII 或 Unicode）。
- `char` 陣列可用於存儲字符串的每個字符。可以用 `String.toCharArray()` 方法轉換字符串為字符陣列。

## 範例
### 基本用法
以下是一些 `char` 的基本使用範例：
```java
public class CharExample {
    public static void main(String[] args) {
        char letter = 'B';
        char digit = '3';
        char symbol = '#';

        System.out.println("Character: " + letter);
        System.out.println("Digit: " + digit);
        System.out.println("Symbol: " + symbol);

        // 使用 Unicode
        char unicodeChar = '\u03A9'; // 希臘字母 Omega
        System.out.println("Unicode Character: " + unicodeChar);
    }
}
```

## 解釋
- **常見陷阱**: 使用 `char` 時，必須注意避免將字符使用雙引號包裹，因為這會被視為字符串 (String) 而非字符 (char)。
- **字元運算**: `char` 可以與整數進行運算，這意味著可以進行字符的加減運算，這在某些情境中非常有用，例如生成字母序列。
- **無法為空**: `char` 不能被賦予 `null` 值，因為它是一個基本數據類型。如果需要表示一個 "無值" 的字符，可以使用特定的字符，例如 `'\u0000'`。

## 一句總結
`char` 是 Java 中用於表示單一字符的基本數據類型，支持 Unicode 編碼並可進行數字運算。