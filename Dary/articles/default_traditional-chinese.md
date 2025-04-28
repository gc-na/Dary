<!--
Meta Description: # Java 中的 "default" 關鍵字：用法與特性 ## 概述 在 Java 編程語言中，"default" 是一個具有特殊意義的關鍵字，主要用於接口的默認方法和 switch 語句中的默認情況。這個關鍵字的出現大大增強了接口的靈活性和易用性。 ## 文檔 ### 目的 "Default" ...
Meta Keywords: default, switch, system, out, println
-->

# Java 中的 "default" 關鍵字：用法與特性

## 概述
在 Java 編程語言中，"default" 是一個具有特殊意義的關鍵字，主要用於接口的默認方法和 switch 語句中的默認情況。這個關鍵字的出現大大增強了接口的靈活性和易用性。

## 文檔
### 目的
"Default" 關鍵字的主要目的是為了在接口中提供默認實現，使得實現該接口的類不必強制實現所有方法，同時也能在 switch 語句中提供對未列舉情況的處理。

### 使用
1. **接口中的默認方法**：
   - 在 Java 8 之後，開發者可以在接口中定義默認方法，這樣實現該接口的類可以選擇性地覆蓋這些方法。
   ```java
   public interface MyInterface {
       default void myDefaultMethod() {
           System.out.println("這是默認方法");
       }
   }
   ```

2. **Switch 語句中的默認情況**：
   - 當 switch 語句中的所有 case 都不匹配時，可以使用 "default" 來處理其他情況。
   ```java
   switch (day) {
       case 1:
           System.out.println("星期一");
           break;
       case 2:
           System.out.println("星期二");
           break;
       default:
           System.out.println("未知的日期");
           break;
   }
   ```

### 詳細說明
- **默認方法**允許在接口中提供方法的具體實現，這樣可以避免在每個實現類中重複代碼。
- **switch 語句的默認情況**確保了程式在未處理的情況下不會發生錯誤，提供了一種安全的方式來處理意外的輸入。

## 示例
### 默認方法示例
```java
public interface Animal {
    default void sound() {
        System.out.println("動物發出的聲音");
    }
}

public class Dog implements Animal {
    @Override
    public void sound() {
        System.out.println("汪汪");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.sound(); // 輸出: 汪汪
    }
}
```

### Switch 語句示例
```java
public class Main {
    public static void main(String[] args) {
        int day = 5;
        switch (day) {
            case 1:
                System.out.println("星期一");
                break;
            case 2:
                System.out.println("星期二");
                break;
            default:
                System.out.println("未知的日期"); // 輸出: 未知的日期
                break;
        }
    }
}
```

## 解釋
- **常見陷阱**：
  - 在接口中定義的默認方法如果被實現類覆蓋，則必須提供具體實現，否則將使用默認實現。
  - 使用 switch 的 default 情況時，應注意其位置，應放在所有 case 的最後，以確保邏輯清晰。

## 總結
"Default" 在 Java 中是用於接口默認方法和 switch 語句中的重要關鍵字，提供了靈活性和可讀性。