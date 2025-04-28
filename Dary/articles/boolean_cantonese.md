<!--
Meta Description: # JAVA Boolean 數據類型：全面指南 ## 摘要 在 JAVA 編程中，Boolean 數據類型用於表示真偽值，這對於控制程序邏輯至關重要。它是編寫條件語句和邏輯運算的基礎。 ## 文件說明 Boolean 是 JAVA 中的一種原始數據類型，用來表示兩個狀態：`true` 或 `fal...
Meta Keywords: boolean, java, system, out, println
-->

# JAVA Boolean 數據類型：全面指南

## 摘要
在 JAVA 編程中，Boolean 數據類型用於表示真偽值，這對於控制程序邏輯至關重要。它是編寫條件語句和邏輯運算的基礎。

## 文件說明
Boolean 是 JAVA 中的一種原始數據類型，用來表示兩個狀態：`true` 或 `false`。這個數據類型在決定程式控制流程時非常重要，尤其是在條件判斷和循環中。

### 目的
- 表示布爾值（真或假）。
- 用於邏輯運算和控制結構。

### 用法
- Boolean 變量的聲明：可以直接聲明 Boolean 型變量並賦值。
- 條件語句：Boolean 值通常用於 `if`、`while`、`for` 等控制結構中。
- 邏輯運算：可以使用 AND（&&）、OR（||）和 NOT（!）等運算符進行布爾運算。

## 範例
以下是使用 Boolean 的基本範例：

```java
public class BooleanExample {
    public static void main(String[] args) {
        boolean isJavaFun = true;
        boolean isFishTasty = false;

        System.out.println("Java 是有趣的嗎？ " + isJavaFun);
        System.out.println("魚好吃嗎？ " + isFishTasty);

        // 使用 if 語句
        if (isJavaFun) {
            System.out.println("Java 是有趣的！");
        } else {
            System.out.println("Java 不有趣！");
        }
    }
}
```

## 解釋
在使用 Boolean 時，有幾個常見的陷阱需要注意：

1. **使用錯誤的運算符**：確保在條件語句中使用正確的布爾邏輯運算符，否則可能導致不預期的結果。
2. **布爾值的初始化**：未初始化的 Boolean 變量會導致編譯錯誤，因此必須在使用前進行初始化。
3. **自動裝箱**：JAVA 中的 Boolean 對象類型和基本類型之間存在自動裝箱和拆箱的過程，需謹慎處理。

## 單行摘要
Boolean 是 JAVA 中的基本數據類型，用於表示真偽值，對程式邏輯控制至關重要。