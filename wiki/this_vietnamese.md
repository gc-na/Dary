<!--
Meta Description: # Từ khóa "this" trong JAVA: Hiểu và Sử Dụng ## Tóm tắt Từ khóa "this" trong JAVA là một tham chiếu đến đối tượng hiện tại trong một lớp. Nó thường đư...
Meta Keywords: trong, public, dụng, biến, gọi
-->

# Từ khóa "this" trong JAVA: Hiểu và Sử Dụng

## Tóm tắt
Từ khóa "this" trong JAVA là một tham chiếu đến đối tượng hiện tại trong một lớp. Nó thường được sử dụng để phân biệt giữa các biến instance và các tham số của phương thức, cũng như để gọi các phương thức và constructor khác trong cùng một lớp.

## Tài liệu
Từ khóa "this" có vai trò rất quan trọng trong lập trình hướng đối tượng bằng JAVA. Khi bạn sử dụng "this", bạn đang chỉ định rõ ràng rằng bạn đang nói đến đối tượng hiện tại đang được xử lý. Điều này rất hữu ích trong các tình huống sau:

1. **Phân biệt giữa biến instance và tham số**: Khi tên biến instance và tham số phương thức trùng nhau, "this" giúp bạn phân biệt chúng.
   
   ```java
   public class Car {
       private String model;

       public Car(String model) {
           this.model = model; // Sử dụng "this" để chỉ đến biến instance
       }
   }
   ```

2. **Gọi phương thức khác trong lớp**: Bạn có thể sử dụng "this" để gọi các phương thức khác trong cùng một lớp.
   
   ```java
   public void displayModel() {
       System.out.println(this.model); // Gọi biến model của đối tượng hiện tại
   }
   ```

3. **Gọi constructor khác**: "this" có thể được sử dụng để gọi một constructor khác trong cùng một lớp.

   ```java
   public Car() {
       this("Default Model"); // Gọi constructor với tham số
   }
   ```

## Ví dụ
Dưới đây là một vài ví dụ minh họa cách sử dụng từ khóa "this":

### Ví dụ 1: Phân biệt giữa biến và tham số
```java
public class Person {
    private String name;

    public Person(String name) {
        this.name = name; // "this.name" là biến instance, "name" là tham số
    }

    public void displayName() {
        System.out.println("Name: " + this.name);
    }
}
```

### Ví dụ 2: Gọi phương thức khác
```java
public class Calculator {
    private int result;

    public void add(int value) {
        this.result += value; // "this.result" chỉ đến biến instance
        this.displayResult();  // Gọi phương thức khác trong cùng lớp
    }

    public void displayResult() {
        System.out.println("Result: " + this.result);
    }
}
```

### Ví dụ 3: Gọi constructor khác
```java
public class Book {
    private String title;

    public Book() {
        this("Unknown Title"); // Gọi constructor khác
    }

    public Book(String title) {
        this.title = title; // Khởi tạo biến instance
    }
}
```

## Giải thích
Khi sử dụng "this", có một số điều cần lưu ý:

- **Tầm quan trọng trong constructor**: Trong constructor, "this" rất hữu ích để tránh nhầm lẫn giữa biến instance và tham số. Nếu không sử dụng "this", bạn có thể vô tình khiến biến instance không được khởi tạo đúng cách.

- **Không thể sử dụng trong static context**: "this" không thể được sử dụng trong các phương thức static vì các phương thức này không liên kết với bất kỳ đối tượng cụ thể nào.

- **Tính chất không thay đổi**: Từ khóa "this" luôn liên kết với đối tượng hiện tại và không thay đổi trong suốt thời gian tồn tại của đối tượng.

## Tóm tắt một câu
Từ khóa "this" trong JAVA được sử dụng để tham chiếu đến đối tượng hiện tại, giúp phân biệt giữa các biến instance và tham số, cũng như gọi các phương thức và constructor khác trong cùng một lớp.