<!--
Meta Description: # JAVA 中的列舉（enum）：全面指南 ## 概要 在 JAVA 程式語言中，列舉（enum）是一種特殊的資料型別，用於定義一組常數，這些常數可以使程式碼更具可讀性和可維護性。列舉使得程式員能夠以更有意義的方式處理固定的值集合。 ## 文檔 ### 目的 列舉（enum）用於定義一組固定的常數...
Meta Keywords: color, enum, java, public, red
-->

# JAVA 中的列舉（enum）：全面指南

## 概要
在 JAVA 程式語言中，列舉（enum）是一種特殊的資料型別，用於定義一組常數，這些常數可以使程式碼更具可讀性和可維護性。列舉使得程式員能夠以更有意義的方式處理固定的值集合。

## 文檔
### 目的
列舉（enum）用於定義一組固定的常數，通常用於表示具體的選項或狀態，增強了程式碼的可讀性和可維護性。

### 用法
在 JAVA 中，列舉的定義使用 `enum` 關鍵字。列舉類型可以具有方法和屬性，並且可以實現介面。列舉類型的每個實例都是列舉類型的唯一實例。

```java
public enum Day {
    SUNDAY, MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY
}
```

### 詳細說明
- **聲明列舉**: 使用 `enum` 關鍵字來聲明列舉類型，並定義其常數值。
- **使用列舉**: 列舉可以用於 `switch` 陳述式、條件判斷等場合，提高代碼的可讀性。
- **方法和屬性**: 列舉中可以定義方法和屬性，這使得列舉不僅僅是一組常數。

## 範例
以下是使用列舉的基本範例：

```java
public enum Color {
    RED, GREEN, BLUE;
}

public class TestEnum {
    Color color;

    public TestEnum(Color color) {
        this.color = color;
    }

    public void displayColor() {
        switch (color) {
            case RED:
                System.out.println("Color is Red.");
                break;
            case GREEN:
                System.out.println("Color is Green.");
                break;
            case BLUE:
                System.out.println("Color is Blue.");
                break;
        }
    }

    public static void main(String[] args) {
        TestEnum test = new TestEnum(Color.RED);
        test.displayColor(); // 輸出: Color is Red.
    }
}
```

## 解釋
### 常見陷阱
- **列舉的比較**: 使用 `==` 來比較列舉值是安全的，但使用 `equals()` 方法可能會引起混淆，因為列舉的實例是唯一的。
- **不能繼承**: 列舉不能繼承其他類別或被繼承，因為它們隱式繼承了 `java.lang.Enum`。
- **序列化**: 列舉實例在序列化過程中是安全的，但必須注意列舉的變更會影響序列化過程。

## 一句總結
JAVA 中的列舉（enum）是一種強類型的資料型別，用於定義一組固定的常數，增強程式碼的可讀性和維護性。