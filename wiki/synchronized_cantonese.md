<!--
Meta Description: # JAVA 的 "synchronized" 關鍵字：多執行緒程式中的同步機制 ## 簡介 在 JAVA 中，`synchronized` 是一個關鍵字，用於控制多執行緒環境中的對共享資源的訪問。它確保同一時間只有一個執行緒可以訪問被標記為同步的代碼區域，從而防止數據不一致和競爭條件的發生。 ##...
Meta Keywords: synchronized, java, public, count, void
-->

# JAVA 的 "synchronized" 關鍵字：多執行緒程式中的同步機制

## 簡介
在 JAVA 中，`synchronized` 是一個關鍵字，用於控制多執行緒環境中的對共享資源的訪問。它確保同一時間只有一個執行緒可以訪問被標記為同步的代碼區域，從而防止數據不一致和競爭條件的發生。

## 文檔
### 目的
`synchronized` 的主要目的是為了實現執行緒的安全性。當多個執行緒同時訪問同一個對象的共享資源時，使用 `synchronized` 可以避免數據破壞和不正確的行為。

### 使用方法
`synchronized` 可以用於方法或代碼塊。其基本語法如下：

1. **同步方法**：
   ```java
   public synchronized void synchronizedMethod() {
       // 需要同步的程式碼
   }
   ```

2. **同步代碼塊**：
   ```java
   public void method() {
       synchronized (this) {
           // 需要同步的程式碼
       }
   }
   ```

在同步代碼塊中，可以使用任何對象作為鎖（lock），通常使用當前對象 (`this`) 來鎖定。

### 詳細信息
- **鎖定對象**：當一個執行緒進入同步方法或代碼塊時，它會獲得對指定對象的鎖。如果另一個執行緒嘗試訪問同一個鎖定對象的同步方法，則該執行緒將被阻塞，直到第一個執行緒釋放鎖。
- **性能影響**：雖然 `synchronized` 保證了執行緒安全，但在高並發場景下，過多的同步可能會導致性能下降，因為它會導致執行緒的上下文切換和阻塞。

## 範例
以下是一個簡單的範例，展示如何使用 `synchronized` 關鍵字來保護共享變數：
```java
class Counter {
    private int count = 0;

    public synchronized void increment() {
        count++;
    }

    public synchronized int getCount() {
        return count;
    }
}
```

在這個範例中，`increment` 和 `getCount` 方法都被標記為同步，確保在任何時候只有一個執行緒可以修改 `count` 變數。

## 解釋
### 常見陷阱
- **死鎖**：如果多個執行緒以不當的順序獲取鎖，可能會導致死鎖的情況，這時候執行緒會互相等待，無法繼續執行。
- **過度同步**：過多的同步會影響性能，尤其是在高並發的環境中，應謹慎使用。

### 注意事項
- 使用 `synchronized` 時，應避免在持有鎖的情況下進行長時間的操作，這樣會降低系統的響應速度。
- 對於需要頻繁訪問的共享資源，可以考慮使用其他並發工具，如 `java.util.concurrent` 包中的 `Lock` 接口，這能提供更靈活的鎖定機制。

## 一句總結
`synchronized` 是 JAVA 中用於實現執行緒安全的關鍵字，能有效防止多執行緒環境中的數據不一致問題。