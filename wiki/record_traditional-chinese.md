<!--
Meta Description: # Java Record: 用於簡化數據類型的創建 ## 概述 Java 的 Record 是一種在 Java 14 中引入的語法結構，用於簡化不變數據類型的創建。透過 Record，開發者可以輕鬆定義只包含數據的類別，並自動生成常用方法如 `toString()`、`equals()` 和 `h...
Meta Keywords: record, java, person, equals, hashcode
-->

# Java Record: 用於簡化數據類型的創建

## 概述
Java 的 Record 是一種在 Java 14 中引入的語法結構，用於簡化不變數據類型的創建。透過 Record，開發者可以輕鬆定義只包含數據的類別，並自動生成常用方法如 `toString()`、`equals()` 和 `hashCode()`，減少樣板代碼的編寫。

## 文檔
Record 的主要目的是提供一種簡潔的方式來創建不可變的數據類型。這意味著一旦 Record 被創建，其屬性就無法被修改。這種特性非常適合用於封裝數據和傳遞數據對象。Record 的語法簡單，使用者只需定義屬性，Java 會自動處理其他細節。

### 使用方法
要定義一個 Record，您可以使用以下語法：

```java
record RecordName(DataType1 field1, DataType2 field2) {}
```

例如，定義一個表示點的 Record：

```java
record Point(int x, int y) {}
```

在這裡，`Point` 是 Record 的名字，`x` 和 `y` 是其字段。

### 詳細信息
- **不可變性**：一旦創建，Record 的屬性無法被更改。
- **自動生成方法**：Java 會自動生成 `toString()`、`equals()` 和 `hashCode()` 方法，使用者無需手動編寫。
- **簡化代碼**：Record 減少了樣板代碼，使得數據類型的定義更加簡潔。
- **可擴展性**：Record 可以實現接口，但不能擴展其他類別。

## 範例
以下是使用 Record 的基本範例：

```java
// 定義一個 Record
record Person(String name, int age) {}

// 創建一個 Person 實例
Person person = new Person("Alice", 30);

// 使用自動生成的方法
System.out.println(person); // 輸出：Person[name=Alice, age=30]
System.out.println(person.name()); // 輸出：Alice
System.out.println(person.age()); // 輸出：30
```

## 解釋
常見的坑和注意事項：
- Record 不能繼承其他類別，因此您無法在 Record 中使用 `extends` 關鍵字。
- Record 也不能是非靜態的內部類別。
- 雖然 Record 自動生成 `equals()` 和 `hashCode()`，但如果需要自定義邏輯，您將需要手動實現這些方法。
- Record 的字段必須是`final`，這意味著它們在創建時必須被初始化。

## 總結
Java 的 Record 是一種強大的語法結構，用於簡化不變數據類型的創建，促進了更清晰、更簡潔的代碼編寫。