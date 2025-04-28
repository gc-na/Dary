<!--
Meta Description: # 在 JAVA 中的 "extends" 關鍵字 ## 概述 在 JAVA 程式語言中，`extends` 是一個關鍵字，用於實現類別之間的繼承關係。透過 `extends`，一個類別可以從另一個類別繼承屬性和方法，從而促進代碼的重用和結構化設計。 ## 文件說明 ### 目的 `extends`...
Meta Keywords: extends, java, class, void, system
-->

# 在 JAVA 中的 "extends" 關鍵字

## 概述
在 JAVA 程式語言中，`extends` 是一個關鍵字，用於實現類別之間的繼承關係。透過 `extends`，一個類別可以從另一個類別繼承屬性和方法，從而促進代碼的重用和結構化設計。

## 文件說明
### 目的
`extends` 主要用於定義一個子類別（subclass），該子類別繼承父類別（superclass）的屬性和行為。這使得子類別可以重用和擴展父類別的功能。

### 使用方式
在 JAVA 中，使用 `extends` 關鍵字的基本語法如下：

```java
class 子類別名稱 extends 父類別名稱 {
    // 子類別的屬性和方法
}
```

### 詳細說明
1. **單一繼承**：JAVA 僅支持單一繼承，即一個類別只能直接繼承一個父類別。如果需要多重繼承的效果，可以通過介面（interface）來實現。
   
2. **父類別的構造函數**：在子類別的構造函數中，可以使用 `super()` 來呼叫父類別的構造函數，以初始化父類別的屬性。

3. **方法重寫**：子類別可以重寫父類別的方法，提供特定的實現。

4. **多型性**：使用 `extends` 的類別構成了JAVA的多型性，允許父類別引用子類別的物件。

## 例子
以下是一個使用 `extends` 的基本範例：

```java
// 定義父類別
class 動物 {
    void 叫() {
        System.out.println("動物叫");
    }
}

// 定義子類別
class 狗 extends 動物 {
    @Override
    void 叫() {
        System.out.println("汪汪");
    }
}

// 主程式
public class 主程式 {
    public static void main(String[] args) {
        動物 myDog = new 狗();
        myDog.叫();  // 輸出: 汪汪
    }
}
```

## 解釋
- **常見陷阱**：在使用 `extends` 時，必須了解 JAVA 的單一繼承限制，若試圖從多個類別同時繼承將會導致編譯錯誤。
  
- **抽象類別**：當父類別是抽象類別時，子類別必須實現所有未實現的方法，否則也必須被定義為抽象類別。

- **父類和子類的關係**：在設計時，應該清楚地定義父類和子類的關係，以避免不必要的複雜性。

## 一句總結
在 JAVA 中，`extends` 關鍵字用於實現類別繼承，促進代碼重用和結構化設計。