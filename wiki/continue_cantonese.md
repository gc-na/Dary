<!--
Meta Description: # JAVA 中的 "continue" 指令：用法與示例 ## 概要 在 JAVA 程式設計中，`continue` 是一個控制流語句，用於跳過當前迴圈中的剩餘代碼，並立即開始下一次迴圈的執行。它主要用於 `for`、`while` 和 `do-while` 迴圈中，以提高程式的可讀性和效率。 #...
Meta Keywords: continue, java, while, int, 迴圈中
-->

# JAVA 中的 "continue" 指令：用法與示例

## 概要
在 JAVA 程式設計中，`continue` 是一個控制流語句，用於跳過當前迴圈中的剩餘代碼，並立即開始下一次迴圈的執行。它主要用於 `for`、`while` 和 `do-while` 迴圈中，以提高程式的可讀性和效率。

## 文檔
`continue` 指令的主要目的是優化迴圈的執行過程。當程式執行到 `continue` 語句時，會跳過該次迴圈中 `continue` 之後的所有代碼，然後根據迴圈的類型進入下一次迴圈迭代。

### 用法
- 在 `for` 迴圈中，`continue` 將直接跳到迴圈的增量部分。
- 在 `while` 或 `do-while` 迴圈中，`continue` 將會重新評估條件表達式。

### 詳細說明
- `continue` 語句可以與 `label` 結合使用，以跳出多層嵌套迴圈。
- `continue` 語句不會終止整個迴圈，而只是跳過當前的迭代。

## 示例
以下是 `continue` 語句的基本使用示例：

### 在 for 迴圈中的使用
```java
for (int i = 0; i < 10; i++) {
    if (i % 2 == 0) {
        continue; // 跳過偶數
    }
    System.out.println(i); // 只會印出奇數
}
```

### 在 while 迴圈中的使用
```java
int i = 0;
while (i < 10) {
    i++;
    if (i % 2 == 0) {
        continue; // 跳過偶數
    }
    System.out.println(i); // 只會印出奇數
}
```

### 在多層嵌套迴圈中的使用
```java
outer: for (int i = 0; i < 5; i++) {
    for (int j = 0; j < 5; j++) {
        if (j == 2) {
            continue outer; // 跳到外層迴圈的下一次迭代
        }
        System.out.println("i: " + i + ", j: " + j);
    }
}
```

## 解釋
在使用 `continue` 時，有幾個常見陷阱和注意事項：
- 確保在使用 `continue` 前，已經明確知道會跳過的代碼部分，否則可能會導致邏輯錯誤。
- 在多層嵌套迴圈中，使用標籤（label）來指明要跳過的具體迴圈，這樣可以避免意外跳出錯誤的迴圈。
- 過度使用 `continue` 可能導致程式碼變得難以閱讀，因此應謹慎選擇使用時機。

## 一句總結
`continue` 是 JAVA 中的控制流語句，用於跳過當前迴圈的剩餘代碼，立即進入下一次迴圈的執行。