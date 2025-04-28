<!--
Meta Description: # Java 中的 synchronized 關鍵字：多執行緒同步的解決方案 ## 摘要 `synchronized` 是 Java 語言中的一個關鍵字，用於控制對共享資源的訪問，確保在多執行緒環境中資料的一致性和完整性。它通過鎖機制來保護方法或代碼塊，避免執行緒之間的競爭條件。 ## 文檔 在 J...
Meta Keywords: synchronized, java, public, count, void
-->

# Java 中的 synchronized 關鍵字：多執行緒同步的解決方案

## 摘要
`synchronized` 是 Java 語言中的一個關鍵字，用於控制對共享資源的訪問，確保在多執行緒環境中資料的一致性和完整性。它通過鎖機制來保護方法或代碼塊，避免執行緒之間的競爭條件。

## 文檔
在 Java 中，當多個執行緒同時訪問同一個資源（如變數或對象）時，可能會導致資料不一致的問題。為了防止這種情況，Java 提供了 `synchronized` 關鍵字，允許開發者進行執行緒同步。

### 目的
`synchronized` 的主要目的是保護共享資源，使得在同一時間只有一個執行緒可以執行被保護的代碼區域，從而避免數據競爭（race condition）。

### 用法
`synchronized` 可以用於方法或代碼塊：
- **同步方法**：在方法聲明中添加 `synchronized` 關鍵字。
- **同步代碼塊**：使用 `synchronized` 包裝代碼塊，並指定鎖對象。

### 詳細說明
- **同步方法**：當一個執行緒進入同步方法時，其他執行緒必須等待，直到該方法執行完成。
  
  ```java
  public synchronized void mySyncMethod() {
      // 這裡是同步代碼
  }
  ```

- **同步代碼塊**：可以更細粒度地控制鎖，選擇特定對象作為鎖來保護代碼塊。
  
  ```java
  public void myMethod() {
      synchronized(this) {
          // 這裡是同步代碼
      }
  }
  ```

## 示例
### 同步方法示例
```java
public class Counter {
    private int count = 0;

    public synchronized void increment() {
        count++;
    }

    public synchronized int getCount() {
        return count;
    }
}
```

### 同步代碼塊示例
```java
public class Counter {
    private int count = 0;

    public void increment() {
        synchronized(this) {
            count++;
        }
    }

    public int getCount() {
        synchronized(this) {
            return count;
        }
    }
}
```

## 解釋
使用 `synchronized` 時需要注意以下幾點：
- **性能影響**：過度使用 `synchronized` 會導致性能瓶頸，因為它會增加執行緒的等待時間。
- **死鎖**：如果多個執行緒相互等待對方釋放鎖，可能會導致死鎖的情況。設計時需避免此情況。
- **可重入鎖**：Java 的 `synchronized` 鎖是可重入的，這意味著同一執行緒可以多次獲得同一鎖，而不會造成死鎖。

## 一句總結
Java 中的 `synchronized` 關鍵字是用於多執行緒編程中，確保共享資源安全的有效解決方案。