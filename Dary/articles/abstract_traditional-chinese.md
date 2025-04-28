<!--
Meta Description: # JAVA 中的抽象 (Abstract) 關鍵字 ## 簡介 在 JAVA 程式設計語言中，`abstract` 關鍵字用於定義抽象類別和抽象方法，這是面向物件編程（OOP）中的一個核心概念。使用 `abstract` 可以幫助開發者設計可擴展的程式架構，促進代碼的重用性和可維護性。 ## 文件...
Meta Keywords: abstract, java, animal, class, void
-->

# JAVA 中的抽象 (Abstract) 關鍵字

## 簡介
在 JAVA 程式設計語言中，`abstract` 關鍵字用於定義抽象類別和抽象方法，這是面向物件編程（OOP）中的一個核心概念。使用 `abstract` 可以幫助開發者設計可擴展的程式架構，促進代碼的重用性和可維護性。

## 文件說明
### 目的
`abstract` 關鍵字的主要目的是允許開發者定義沒有具體實現的方法，這些方法必須在子類中被實現。這一特性使得開發者可以創建通用的類別結構，強制子類提供具體的實現。

### 用法
在 JAVA 中，`abstract` 可以用於：
1. **抽象類別**：使用 `abstract` 關鍵字來修飾類別，表示該類別不可被實例化，並且可以包含抽象方法和具體方法。
2. **抽象方法**：在抽象類別中定義的方法，使用 `abstract` 關鍵字修飾，沒有方法體，需由子類提供具體實現。

### 詳細說明
- 抽象類別的定義：`abstract class ClassName { ... }`
- 抽象方法的定義：`abstract returnType methodName(parameters);`
- 抽象類別可以包含構造函數、屬性和具體方法。
- 繼承抽象類別的子類必須實現所有抽象方法，否則該子類也必須被聲明為抽象類別。
- 抽象類別可以實現接口，並且可以被其他類別擴展。

## 範例
### 基本用法範例
```java
// 定義抽象類別
abstract class Animal {
    abstract void sound(); // 抽象方法

    void sleep() { // 具體方法
        System.out.println("Animal is sleeping");
    }
}

// 繼承抽象類別
class Dog extends Animal {
    void sound() {
        System.out.println("Bark");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal myDog = new Dog(); // 創建 Dog 的實例
        myDog.sound(); // 輸出: Bark
        myDog.sleep(); // 輸出: Animal is sleeping
    }
}
```

## 解釋
### 常見的陷阱與注意事項
- **未實現抽象方法**：如果子類未實現所有抽象方法，則需將子類也聲明為抽象，否則編譯器會報錯。
- **不能實例化抽象類別**：嘗試創建抽象類別的實例會導致編譯錯誤。
- **抽象方法不能有方法體**：抽象方法必須是純粹的聲明，不能包含任何實現。

## 一句話總結
`abstract` 關鍵字在 JAVA 中用於定義抽象類別和抽象方法，促進程式的可擴展性與可維護性。