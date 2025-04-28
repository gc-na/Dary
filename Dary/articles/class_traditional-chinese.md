<!--
Meta Description: # JAVA 類別（Class）概述與使用指南 ## 摘要 在 JAVA 程式語言中，「類別」是物件導向編程的核心概念之一，定義了物件的屬性和行為，是構建應用程式的重要基石。 ## 文檔 ### 目的 類別（Class）在 JAVA 中是一個藍圖，描述了物件的屬性（變數）和行為（方法）。使用類別，開...
Meta Keywords: java, class, public, string, color
-->

# JAVA 類別（Class）概述與使用指南

## 摘要
在 JAVA 程式語言中，「類別」是物件導向編程的核心概念之一，定義了物件的屬性和行為，是構建應用程式的重要基石。

## 文檔
### 目的
類別（Class）在 JAVA 中是一個藍圖，描述了物件的屬性（變數）和行為（方法）。使用類別，開發者可以創建物件，而物件是類別的實例。

### 使用方式
類別的基本語法如下：
```java
class ClassName {
    // 屬性
    Type attributeName;

    // 構造函數
    ClassName() {
        // 初始化屬性
    }

    // 方法
    ReturnType methodName(ParameterType parameterName) {
        // 方法體
    }
}
```
- **定義類別**：使用 `class` 關鍵字後接類別名稱。
- **屬性**：在類別中定義變數來表示物件的特徵。
- **構造函數**：特殊的方法，用於初始化新創建的物件。
- **方法**：定義物件的行為或功能。

### 詳細說明
- **存取修飾符**：類別可以使用存取修飾符（如 `public`、`private`、`protected`）來控制其可見性。
- **繼承**：類別可以從其他類別繼承屬性和方法，使用 `extends` 關鍵字。
- **介面**：類別可以實現介面，使用 `implements` 關鍵字，這提供了一種多重繼承的方式。
- **抽象類別與介面**：抽象類別不能被實例化，並且可以包含抽象方法；介面只包含方法的聲明，沒有實作。

## 範例
以下是一個簡單的 JAVA 類別範例：

```java
public class Car {
    // 屬性
    private String color;
    private String model;

    // 構造函數
    public Car(String color, String model) {
        this.color = color;
        this.model = model;
    }

    // 方法
    public void displayInfo() {
        System.out.println("車輛顏色: " + color + ", 車型: " + model);
    }
}

// 使用範例
public class Main {
    public static void main(String[] args) {
        Car myCar = new Car("紅色", "Toyota");
        myCar.displayInfo(); // 輸出: 車輛顏色: 紅色, 車型: Toyota
    }
}
```

## 解釋
- **常見錯誤**：初學者經常會忘記使用 `new` 關鍵字來創建類別的實例，或者在方法中使用未定義的變數。
- **命名規則**：類別名稱應使用 Pascal 命名法，首字母大寫，並且應該具有描述性。
- **類別與物件**：類別是設計藍圖，而物件是這個藍圖的具體實現。有效地使用類別可以幫助開發者創建可重用的代碼。

## 一句總結
在 JAVA 中，類別是物件導向編程的基礎，通過定義屬性和方法來構建可重用的程式碼結構。