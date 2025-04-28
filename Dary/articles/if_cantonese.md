<!--
Meta Description: # JAVA 的 "if" 條件語句：控制程序流程的基石 ## 概要 在 JAVA 中，"if" 條件語句是一種控制結構，允許程序根據布林表達式的評估結果來決定是否執行特定代碼塊。 ## 文檔 "if" 語句的主要目的在於提供程序的決策能力。當條件為真（true）時，會執行相應的代碼塊，否則將跳過這...
Meta Keywords: else, java, system, out, println
-->

# JAVA 的 "if" 條件語句：控制程序流程的基石

## 概要
在 JAVA 中，"if" 條件語句是一種控制結構，允許程序根據布林表達式的評估結果來決定是否執行特定代碼塊。

## 文檔
"if" 語句的主要目的在於提供程序的決策能力。當條件為真（true）時，會執行相應的代碼塊，否則將跳過這段代碼。這使得開發者能夠根據不同的情況執行不同的操作，從而使程序具有靈活性。

### 使用方式
"if" 語句的基本語法如下：

```java
if (condition) {
    // 當 condition 為 true 時執行的代碼
}
```

此外，JAVA 還支持 "if-else" 和 "if-else if" 結構，以處理多個條件：

```java
if (condition1) {
    // 當 condition1 為 true 時執行的代碼
} else if (condition2) {
    // 當 condition2 為 true 時執行的代碼
} else {
    // 當所有條件均為 false 時執行的代碼
}
```

## 範例
以下是一些基本的 "if" 語句使用示例：

### 範例 1：簡單的 if 語句
```java
int number = 10;
if (number > 5) {
    System.out.println("數字大於 5");
}
```

### 範例 2：if-else 語句
```java
int number = 3;
if (number % 2 == 0) {
    System.out.println("數字是偶數");
} else {
    System.out.println("數字是奇數");
}
```

### 範例 3：if-else if 語句
```java
int score = 85;
if (score >= 90) {
    System.out.println("成績優秀");
} else if (score >= 75) {
    System.out.println("成績良好");
} else {
    System.out.println("成績需要改進");
}
```

## 解釋
在使用 "if" 語句時，有幾個常見的陷阱需要注意：

1. **條件邏輯錯誤**：確保條件表達式的邏輯正確，例如使用 `==` 進行比較，而不是 `=`（賦值運算符）。
2. **大括號的使用**：即使只有一行代碼，也建議始終使用大括號 `{}`，以提高可讀性並減少錯誤的可能性。
3. **else 和 else if 的順序**：注意條件的順序，因為優先匹配的條件將會被執行，後面的條件將不再評估。

## 單行總結
"if" 語句是 JAVA 中實現條件邏輯的基本工具，允許根據特定條件執行代碼塊。