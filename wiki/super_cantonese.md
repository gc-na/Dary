<!--
Meta Description: # Java 中的 "super" 關鍵字：用途與示例 ## 簡介 在 Java 編程中，"super" 是一個關鍵字，用於對父類中的屬性和方法進行引用。它允許子類訪問父類的成員，進而實現繼承和多態性。 ## 文檔 ### 目的 "super" 關鍵字的主要目的是在子類中訪問父類的成員，包括方法和變...
Meta Keywords: super, dog, animal, class, java
-->

# Java 中的 "super" 關鍵字：用途與示例

## 簡介
在 Java 編程中，"super" 是一個關鍵字，用於對父類中的屬性和方法進行引用。它允許子類訪問父類的成員，進而實現繼承和多態性。

## 文檔
### 目的
"super" 關鍵字的主要目的是在子類中訪問父類的成員，包括方法和變量。這使得子類可以重用父類的代碼，從而提高代碼的可維護性和可讀性。

### 用法
1. **調用父類構造函數**：在子類的構造函數中使用 `super()` 可以調用父類的構造函數。
2. **訪問父類方法**：通過 `super.methodName()` 調用父類的方法，特別是在子類中重寫了父類的方法後。
3. **訪問父類變量**：使用 `super.variableName` 可以訪問父類的變量，尤其是在子類中有同名變量的情況下。

### 詳細說明
- 使用 "super" 時，必須確保父類中存在被調用的成員。
- "super" 只能在子類的上下文中使用，無法在靜態上下文中使用。
- 當子類和父類中有同名變量時，使用 "super" 可以區分它們。

## 示例
### 1. 調用父類構造函數
```java
class Animal {
    Animal() {
        System.out.println("Animal constructor");
    }
}

class Dog extends Animal {
    Dog() {
        super(); // 調用父類 Animal 的構造函數
        System.out.println("Dog constructor");
    }
}

public class Test {
    public static void main(String[] args) {
        Dog dog = new Dog();
    }
}
```

### 2. 訪問父類方法
```java
class Animal {
    void sound() {
        System.out.println("Animal sound");
    }
}

class Dog extends Animal {
    void sound() {
        super.sound(); // 調用父類方法
        System.out.println("Bark");
    }
}

public class Test {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.sound();
    }
}
```

### 3. 訪問父類變量
```java
class Animal {
    String type = "Animal";
}

class Dog extends Animal {
    String type = "Dog";

    void display() {
        System.out.println("Type: " + super.type); // 使用 super 訪問父類變量
    }
}

public class Test {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.display();
    }
}
```

## 解釋
- **常見陷阱**：在子類中重寫父類方法時，若不使用 `super`，將無法調用父類的原始實現，可能導致預期外的行為。
- **命名衝突**：當子類與父類存在相同名稱的變量時，必須使用 `super` 來明確指定要訪問父類的變量。
- **構造函數**：如果沒有明確調用父類的構造函數，Java 將自動添加 `super()` 來調用父類的無參構造函數，這可能會引發錯誤，如果父類沒有默認構造函數的話。

## 一句總結
在 Java 中，"super" 關鍵字用於在子類中訪問父類的成員，促進代碼的重用和維護。