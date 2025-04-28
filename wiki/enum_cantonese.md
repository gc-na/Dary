<!--
Meta Description: # Java 枚舉 (enum) 的全面指南 ## 概述 Java 中的枚舉（enum）是一種特殊的類型，用於定義一組常量。它使代碼更具可讀性和可維護性，可用於表示固定的、有限的選項，如星期幾、顏色等。 ## 文檔 ### 目的 在 Java 中，枚舉類型用來定義一組預定義的常量，這不僅增加了代碼的...
Meta Keywords: java, enum, public, string, chinesename
-->

# Java 枚舉 (enum) 的全面指南

## 概述
Java 中的枚舉（enum）是一種特殊的類型，用於定義一組常量。它使代碼更具可讀性和可維護性，可用於表示固定的、有限的選項，如星期幾、顏色等。

## 文檔
### 目的
在 Java 中，枚舉類型用來定義一組預定義的常量，這不僅增加了代碼的可讀性，還能減少錯誤的發生。使用枚舉可以方便地管理和使用這些常量。

### 使用方法
在 Java 中，使用 `enum` 關鍵字來定義枚舉。下面是基本的語法結構：

```java
enum EnumName {
    CONSTANT1,
    CONSTANT2,
    CONSTANT3;
}
```

例如，若要定義一個表示季節的枚舉，可以這樣寫：

```java
enum Season {
    WINTER,
    SPRING,
    SUMMER,
    FALL;
}
```

### 詳細說明
- **定義**: 枚舉是一種特殊的類，並且每個常量都是這個類的實例。
- **方法**: 可以在枚舉中定義方法，可以添加字段和構造函數。舉個例子：

```java
enum Day {
    MONDAY("一"),
    TUESDAY("二"),
    WEDNESDAY("三");

    private String chineseName;

    Day(String chineseName) {
        this.chineseName = chineseName;
    }

    public String getChineseName() {
        return chineseName;
    }
}
```

- **使用**: 你可以使用 `switch` 語句來處理枚舉類型。例如：

```java
Day today = Day.WEDNESDAY;

switch (today) {
    case MONDAY:
        System.out.println("今天是星期一");
        break;
    case TUESDAY:
        System.out.println("今天是星期二");
        break;
    case WEDNESDAY:
        System.out.println("今天是星期三");
        break;
}
```

## 示例
### 基本用法
以下範例展示了如何使用枚舉來表示顏色：

```java
enum Color {
    RED,
    GREEN,
    BLUE;
}

public class Main {
    public static void main(String[] args) {
        Color myColor = Color.RED;
        System.out.println("我的顏色是: " + myColor);
    }
}
```

### 帶方法的枚舉
```java
enum TrafficLight {
    RED(30),
    YELLOW(5),
    GREEN(25);

    private int duration; // 持續時間（秒）

    TrafficLight(int duration) {
        this.duration = duration;
    }

    public int getDuration() {
        return duration;
    }
}

public class Main {
    public static void main(String[] args) {
        for (TrafficLight light : TrafficLight.values()) {
            System.out.println(light + " 持續時間: " + light.getDuration() + " 秒");
        }
    }
}
```

## 說明
- **常見陷阱**: 不要使用 `enum` 定義的常量與數字或字符串進行比較，應始終使用 `enum` 提供的實例進行比較。
- **擴展性**: 雖然枚舉提供了一個靜態的常量集合，但可以在需要時擴展功能，例如添加方法和屬性。
- **序列化**: 枚舉能夠自動序列化，這使得在分佈式應用程序中傳遞枚舉變得更加容易。

## 一句總結
Java 中的枚舉（enum）是一種方便的方式來定義一組固定的常量，從而增強代碼的可讀性和可維護性。