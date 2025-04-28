<!--
Meta Description: # Java 介面 (Interface) 使用指南 ## 概述 在 Java 程式設計中，介面是一種特殊的類型，用於定義一組方法的簽名，這些方法可以被任何實現該介面的類別所實現。介面提供了一種契約，確保實現它的類別遵循特定的行為模式。 ## 文檔 ### 目的 介面在 Java 中的主要目的是提供...
Meta Keywords: java, public, void, implements, class
-->

# Java 介面 (Interface) 使用指南

## 概述
在 Java 程式設計中，介面是一種特殊的類型，用於定義一組方法的簽名，這些方法可以被任何實現該介面的類別所實現。介面提供了一種契約，確保實現它的類別遵循特定的行為模式。

## 文檔
### 目的
介面在 Java 中的主要目的是提供一種抽象的方式來設計類別，使得不同的類別可以使用相同的方法而不需要關心其具體實現。這有助於實現多型（Polymorphism）和解耦（Decoupling），增強系統的可擴展性和可維護性。

### 使用
在 Java 中，介面使用 `interface` 關鍵字來聲明。介面的成員都是公共（public）的，且默認為抽象（abstract），這意味著不可以有方法實現（implementation）。類別可以通過 `implements` 關鍵字來實現介面。

```java
interface Animal {
    void sound(); // 介面中的方法只有聲明，沒有實現
}

class Dog implements Animal {
    public void sound() {
        System.out.println("汪汪");
    }
}

class Cat implements Animal {
    public void sound() {
        System.out.println("喵喵");
    }
}
```

## 範例
以下是介面的基本用法範例：

```java
// 定義介面
interface Vehicle {
    void accelerate(); // 宣告加速方法
}

// 實現介面的類別
class Car implements Vehicle {
    public void accelerate() {
        System.out.println("汽車加速");
    }
}

class Bicycle implements Vehicle {
    public void accelerate() {
        System.out.println("自行車加速");
    }
}

// 主程式
public class Main {
    public static void main(String[] args) {
        Vehicle myCar = new Car();
        Vehicle myBicycle = new Bicycle();
        
        myCar.accelerate(); // 輸出: 汽車加速
        myBicycle.accelerate(); // 輸出: 自行車加速
    }
}
```

## 解釋
### 常見陷阱
1. **多重繼承**: Java 不支持類別的多重繼承，但一個類別可以實現多個介面，這樣可以達到相似的效果。
2. **默認方法**: 從 Java 8 開始，介面可以擁有默認實現的方法，這意味著可以在介面中提供方法的實現。
3. **靜態方法**: Java 8 也允許在介面中定義靜態方法，但這些方法不能被實現類別覆蓋。

### 附加說明
- 介面可以包含常量，這些常量都是 `public static final` 的。
- 介面也可以擴展其他介面，這樣可以構建更複雜的類型系統。

## 一句話總結
介面是 Java 中用於定義方法簽名的一種抽象類型，通過實現介面，類別可以遵循特定的行為契約。