<!--
Meta Description: # Java 中的 "super" 關鍵字：用途與範例 ## 簡介 在 Java 程式語言中，`super` 是一個關鍵字，用於引用父類別的屬性和方法。這個關鍵字在物件導向編程中扮演著重要角色，特別是在繼承的上下文中。 ## 文檔 `super` 關鍵字的主要用途是使子類別能夠訪問其父類別的成員（屬...
Meta Keywords: super, name, dog, java, string
-->

# Java 中的 "super" 關鍵字：用途與範例

## 簡介
在 Java 程式語言中，`super` 是一個關鍵字，用於引用父類別的屬性和方法。這個關鍵字在物件導向編程中扮演著重要角色，特別是在繼承的上下文中。

## 文檔
`super` 關鍵字的主要用途是使子類別能夠訪問其父類別的成員（屬性和方法）。當子類別需要使用父類別的功能時，可以使用 `super` 來明確指定這些成員。這在方法重寫和避免命名衝突時特別有用。

### 使用
- **調用父類別建構子**：使用 `super()` 語法來調用父類別的建構子。
- **訪問父類別的方法**：使用 `super.methodName()` 來調用父類別的特定方法。
- **訪問父類別的屬性**：使用 `super.variableName` 來訪問父類別的屬性。

## 範例
以下是 `super` 關鍵字的基本使用範例：

```java
class Animal {
    String name;

    Animal(String name) {
        this.name = name;
    }

    void speak() {
        System.out.println("動物發聲");
    }
}

class Dog extends Animal {
    
    Dog(String name) {
        super(name); // 調用父類別的建構子
    }

    void speak() {
        super.speak(); // 調用父類別的方法
        System.out.println("汪汪！");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog("小狗");
        dog.speak(); // 輸出：動物發聲\n汪汪！
    }
}
```

## 解釋
- **常見陷阱**：在子類別中，使用 `super` 時必須確保父類別的成員是可見的。如果父類別的成員是私有的，則無法使用 `super` 直接訪問。
- **建構子調用**：如果未明確調用父類別的建構子，Java 編譯器將自動調用無參數建構子。若父類別沒有無參數建構子，則必須手動調用其他建構子。
- **命名衝突**：當子類別和父類別有相同名稱的屬性時，使用 `super` 可以清楚地指向父類別的屬性，以避免混淆。

## 一句總結
`super` 關鍵字在 Java 中用於訪問父類別的屬性和方法，尤其在物件導向編程的繼承中非常重要。