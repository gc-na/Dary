<!--
Meta Description: # Java 中的 "default" 關鍵字：用途及示例 ## 簡介 在 Java 編程中，"default" 關鍵字通常用於接口中，以定義預設方法。這使得開發者可以在不影響現有實現的情況下向接口添加新方法，提升了接口的靈活性和可擴展性。 ## 文件說明 ### 目的 "Default" 關鍵字的...
Meta Keywords: default, void, display, java, public
-->

# Java 中的 "default" 關鍵字：用途及示例

## 簡介
在 Java 編程中，"default" 關鍵字通常用於接口中，以定義預設方法。這使得開發者可以在不影響現有實現的情況下向接口添加新方法，提升了接口的靈活性和可擴展性。

## 文件說明
### 目的
"Default" 關鍵字的主要目的是在接口中提供預設實現，從而允許類實現接口而無需提供所有方法的具體實現。這一特性於 Java 8 引入，旨在簡化接口的使用和增強向後兼容性。

### 用法
在接口方法前加上 "default" 關鍵字，並提供方法體。這樣，實現接口的類可以選擇使用這個預設方法，也可以自行覆蓋該方法。

#### 語法：
```java
interface InterfaceName {
    default void methodName() {
        // 預設實現
    }
}
```

### 詳細說明
- **預設方法**：類實現接口時，若沒有提供對應的具體實現，則會自動使用接口中的預設方法。
- **多重繼承**：若一個類實現多個接口，且這些接口都有相同的預設方法，則該類必須覆蓋此方法以消除歧義。
- **靜態方法**：預設方法的定義不應與靜態方法混淆，靜態方法不能被繼承。

## 示例
以下是使用 "default" 關鍵字的基本範例：

### 範例 1：簡單的預設方法
```java
interface Greeting {
    default void sayHello() {
        System.out.println("Hello, World!");
    }
}

class EnglishGreeting implements Greeting {
    // 使用預設方法
}

class CustomGreeting implements Greeting {
    @Override
    public void sayHello() {
        System.out.println("Hello, Custom World!");
    }
}

public class Main {
    public static void main(String[] args) {
        Greeting english = new EnglishGreeting();
        english.sayHello(); // 輸出: Hello, World!

        Greeting custom = new CustomGreeting();
        custom.sayHello(); // 輸出: Hello, Custom World!
    }
}
```

### 範例 2：處理多重繼承
```java
interface A {
    default void display() {
        System.out.println("Display from A");
    }
}

interface B {
    default void display() {
        System.out.println("Display from B");
    }
}

class C implements A, B {
    @Override
    public void display() {
        A.super.display(); // 可以選擇調用 A 或 B 的顯示方法
    }
}

public class Main {
    public static void main(String[] args) {
        C obj = new C();
        obj.display(); // 輸出: Display from A
    }
}
```

## 解釋
- **共同陷阱**：在多重繼承的情況下，未覆蓋預設方法可能導致編譯錯誤，因為編譯器無法確定應使用哪一個實現。
- **接口擴展性**：使用預設方法可在不破壞現有實現的情況下擴展接口，這在設計大型系統時特別重要。
- **不應該過度使用預設方法**：雖然它們提供了便利，但過度使用可能導致接口的複雜性增加，影響可讀性和可維護性。

## 一句話總結
Java 中的 "default" 關鍵字允許接口提供預設方法實現，從而提升接口的靈活性和向後兼容性。