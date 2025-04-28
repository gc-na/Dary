<!--
Meta Description: # JAVA 中的 Record：簡介與使用指南 ## 概要 在 JAVA 中，`record` 是一種特殊的類，用於簡化數據載體的創建。它提供了一個簡潔的語法來定義不可變的數據結構，並自動生成標準方法，如 `equals()`、`hashCode()` 和 `toString()`，使開發者能夠更...
Meta Keywords: record, person, java, public, name
-->

# JAVA 中的 Record：簡介與使用指南

## 概要
在 JAVA 中，`record` 是一種特殊的類，用於簡化數據載體的創建。它提供了一個簡潔的語法來定義不可變的數據結構，並自動生成標準方法，如 `equals()`、`hashCode()` 和 `toString()`，使開發者能夠更加高效地處理數據。

## 文檔
### 目的
`record` 類的主要目的是提供一種簡單的方式來創建只包含數據的類，這些類通常不需要額外的行為或邏輯。這使得代碼更易於維護和理解。

### 使用方式
在 JAVA 中，定義一個 `record` 類的語法如下：

```java
public record RecordName(Type1 field1, Type2 field2) { }
```

- `RecordName` 是您定義的記錄類名。
- `field1` 和 `field2` 是記錄的字段，並且必須指定其類型。

### 詳細信息
- **不可變性**：`record` 中的字段是自動設置為 `final`，意味著一旦創建後，它們的值不能更改。
- **自動生成方法**：編譯器會自動生成 `equals()`、`hashCode()` 和 `toString()` 方法，這簡化了代碼並提高了可讀性。
- **解構**：可以通過記錄的名稱來直接獲取字段值，無需額外的 getter 方法。

## 範例
以下是定義和使用 `record` 的基本範例：

```java
public record Person(String name, int age) { }

public class Main {
    public static void main(String[] args) {
        Person person = new Person("Alice", 30);
        System.out.println(person.name()); // 輸出: Alice
        System.out.println(person.age());  // 輸出: 30
        System.out.println(person);         // 輸出: Person[name=Alice, age=30]
    }
}
```

## 解釋
- **常見陷阱**：`record` 不支持繼承，這意味著您不能使 `record` 繼承自其他類。這可能會對某些設計模式造成挑戰。
- **不可變性注意**：由於 `record` 中的字段是不可變的，您應在創建記錄時確保提供正確的初始值。
- **擴展性**：如果需要更複雜的行為，您可能需要考慮傳統類或使用組合模式。

## 一句總結
在 JAVA 中，`record` 提供了一種簡單且有效的方式來創建不可變數據載體，從而提高代碼的可讀性和可維護性。