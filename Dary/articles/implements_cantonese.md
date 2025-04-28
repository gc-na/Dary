<!--
Meta Description: # Java 中的 "implements" 關鍵字 ## 簡介 在 Java 編程語言中，`implements` 是一個關鍵字，用於實現接口（interface）。它允許類別承諾執行接口中定義的方法，從而實現多重繼承的行為。 ## 文檔 ### 目的 `implements` 關鍵字的主要目的是...
Meta Keywords: implements, java, class, animal, sound
-->

# Java 中的 "implements" 關鍵字

## 簡介
在 Java 編程語言中，`implements` 是一個關鍵字，用於實現接口（interface）。它允許類別承諾執行接口中定義的方法，從而實現多重繼承的行為。

## 文檔
### 目的
`implements` 關鍵字的主要目的是使類別能夠實現一個或多個接口，這樣類別就可以使用接口中聲明的方法，並提供具體的實現。

### 用法
在定義類別時，使用 `implements` 來指定它所實現的接口。語法如下：

```java
class ClassName implements InterfaceName {
    // 實現接口的方法
}
```

可以同時實現多個接口，使用逗號分隔：

```java
class ClassName implements Interface1, Interface2 {
    // 實現接口的方法
}
```

### 詳細說明
- 接口是一種特殊的引用類型，類似於類，但只能包含常量和方法聲明（沒有具體實現）。
- 當類實現接口時，必須提供接口中所有方法的具體實現，否則類將被視為抽象類，並且必須使用 `abstract` 關鍵字來聲明。
- 接口的實現允許類之間進行更靈活的交互，促進了多態性和可擴展性。

## 範例
以下是一個使用 `implements` 的簡單示例：

```java
// 定義一個接口
interface Animal {
    void sound(); // 接口中的方法聲明
}

// 實現接口的類
class Dog implements Animal {
    @Override
    public void sound() {
        System.out.println("Woof");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal myDog = new Dog(); // 創建接口類型的變量
        myDog.sound(); // 調用實現的聲音方法
    }
}
```
在這個例子中，`Dog` 類實現了 `Animal` 接口，並提供了 `sound` 方法的具體實現。

## 解釋
- **常見問題**：類別實現接口時，必須重寫接口中的所有抽象方法。如果漏掉任何一個，編譯器會報錯。
- **注意事項**：實現多個接口時，若不同接口中有相同方法名稱，則只需實現一次，這樣可以避免重複代碼。
- **接口與抽象類的區別**：接口只能包含方法聲明，無法有實例變量。而抽象類可以有具體方法和實例變量。

## 一句總結
在 Java 中，`implements` 關鍵字用於實現接口，允許類提供接口中方法的具體實現。