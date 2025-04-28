<!--
Meta Description: # Java 中的布林值 (boolean) ## 摘要 在 Java 程式語言中，布林值 (boolean) 是一種基本數據類型，用於表示真 (true) 或假 (false) 的邏輯值，廣泛用於控制流程和條件判斷。 ## 文檔 ### 目的 布林值是 Java 中的基本數據類型之一，主要用於儲存...
Meta Keywords: java, boolean, false, true, system
-->

# Java 中的布林值 (boolean)

## 摘要
在 Java 程式語言中，布林值 (boolean) 是一種基本數據類型，用於表示真 (true) 或假 (false) 的邏輯值，廣泛用於控制流程和條件判斷。

## 文檔
### 目的
布林值是 Java 中的基本數據類型之一，主要用於儲存二元邏輯狀態。它在控制流程（如 if 語句和 while 迴圈）中扮演著重要角色，幫助程式執行不同的操作。

### 用法
在 Java 中，布林值的聲明和使用相當簡單。可以使用 `boolean` 關鍵字來聲明變數，並將其初始化為 `true` 或 `false`。

```java
boolean isJavaFun = true;
boolean isFishTasty = false;
```

### 詳細說明
- **布林類型的範圍**: 布林變數只能取 `true` 或 `false` 兩個值，這使得它在條件判斷中非常高效。
- **條件語句**: 布林值常用於控制語句中，例如 `if`、`while` 和 `for`，以確定程式的執行路徑。
- **布林運算**: Java 還支持布林運算，如邏輯與（&&）、邏輯或（||）和邏輯非（!），可用於進行更複雜的條件評估。

## 範例
### 基本用法
```java
public class BooleanExample {
    public static void main(String[] args) {
        boolean isSunny = true;
        boolean isWeekend = false;

        if (isSunny) {
            System.out.println("今天是晴天！");
        } else {
            System.out.println("今天不是晴天。");
        }

        if (isWeekend) {
            System.out.println("今天是週末！");
        } else {
            System.out.println("今天不是週末。");
        }
    }
}
```

### 布林運算
```java
public class BooleanOperations {
    public static void main(String[] args) {
        boolean a = true;
        boolean b = false;

        System.out.println("a && b: " + (a && b));  // false
        System.out.println("a || b: " + (a || b));  // true
        System.out.println("!a: " + (!a));            // false
    }
}
```

## 說明
### 常見陷阱
1. **布林值的默認值**: 在類中聲明的布林變數會自動初始化為 `false`，這可能導致意外行為。
2. **與其他數據類型的比較**: 布林值不能與整數或其他類型直接比較，可能會引發編譯錯誤。
3. **布林運算的優先級**: 在複雜的條件表達式中，必須注意運算的優先級，以免出現邏輯錯誤。

## 總結
在 Java 中，布林值是一種基本但關鍵的數據類型，廣泛應用於控制流和邏輯運算。