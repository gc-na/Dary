<!--
Meta Description: # Java 類別 (Class) 的全面指南 ## 概述 在 Java 中，類別（Class）是物件導向程序設計的核心概念，允許開發人員創建自定義資料類型，以便於封裝資料和行為。 ## 文檔 類別是 Java 中用來定義物件的藍圖。它包含了屬性（變數）和方法（函數），並且可以被用來創建物件的實例。...
Meta Keywords: java, public, model, year, attribute
-->

# Java 類別 (Class) 的全面指南

## 概述
在 Java 中，類別（Class）是物件導向程序設計的核心概念，允許開發人員創建自定義資料類型，以便於封裝資料和行為。

## 文檔
類別是 Java 中用來定義物件的藍圖。它包含了屬性（變數）和方法（函數），並且可以被用來創建物件的實例。類別的主要目的是組織和管理程式碼，使得程式設計更加模組化和可維護。

### 目的
- 封裝資料與行為。
- 提高代碼的重用性。
- 支持多型性，讓同一接口能夠操作不同數據類型。

### 使用
在 Java 中定義類別的基本語法如下：

```java
public class ClassName {
    // 屬性
    private int attribute;

    // 建構子
    public ClassName(int attribute) {
        this.attribute = attribute;
    }

    // 方法
    public void display() {
        System.out.println("Attribute: " + attribute);
    }
}
```

## 範例
以下是一個簡單的類別範例，展示了如何定義和使用類別：

```java
public class Car {
    private String model;
    private int year;

    // 建構子
    public Car(String model, int year) {
        this.model = model;
        this.year = year;
    }

    // 方法
    public void displayInfo() {
        System.out.println("Model: " + model + ", Year: " + year);
    }

    public static void main(String[] args) {
        Car myCar = new Car("Toyota", 2020);
        myCar.displayInfo(); // 輸出: Model: Toyota, Year: 2020
    }
}
```

## 解釋
在使用類別時，有幾個常見的注意事項：

1. **訪問修飾符**：類別的屬性和方法可以使用不同的訪問修飾符（如 public、private、protected）來控制可見性，這對保護資料非常重要。
2. **建構子**：類別的建構子用於初始化物件，若未定義建構子，Java 將自動提供一個默認建構子。
3. **繼承與多型性**：Java 支持類別的繼承，允許一個類別從另一個類別繼承屬性和方法，這使得代碼更具靈活性和可重用性。

## 一句總結
Java 類別是創建物件的藍圖，封裝了屬性和行為，支持物件導向程序設計的核心原則。