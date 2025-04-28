<!--
Meta Description: # Từ Khóa "static" trong Java: Tính Năng Quan Trọng của Ngôn Ngữ Lập Trình ## Tóm tắt Từ khóa `static` trong Java được sử dụng để khai báo các thành v...
Meta Keywords: tĩnh, biến, các, phương, thức
-->

# Từ Khóa "static" trong Java: Tính Năng Quan Trọng của Ngôn Ngữ Lập Trình

## Tóm tắt
Từ khóa `static` trong Java được sử dụng để khai báo các thành viên (biến và phương thức) thuộc về lớp thay vì thuộc về các đối tượng của lớp đó. Điều này cho phép truy cập trực tiếp đến các thành viên mà không cần phải tạo ra một đối tượng của lớp.

## Tài liệu
### Mục đích
Từ khóa `static` được sử dụng trong Java để:
- Khai báo các biến tĩnh mà sẽ được chia sẻ giữa tất cả các đối tượng của lớp.
- Tạo ra các phương thức tĩnh mà có thể được gọi mà không cần khởi tạo một đối tượng của lớp.

### Cách sử dụng
- **Biến tĩnh**: Khi một biến được khai báo là `static`, nó sẽ có một bản sao duy nhất cho tất cả các đối tượng của lớp.
- **Phương thức tĩnh**: Phương thức được khai báo là `static` có thể được gọi mà không cần phải tạo một thực thể của lớp.

Cú pháp:
```java
class ClassName {
    static dataType variableName; // Biến tĩnh
    static returnType methodName() { // Phương thức tĩnh
        // Thân phương thức
    }
}
```

### Chi tiết
- Biến tĩnh thường được sử dụng để lưu trữ các hằng số hoặc các giá trị cần chia sẻ giữa tất cả các đối tượng.
- Phương thức tĩnh không thể truy cập trực tiếp vào các biến hoặc phương thức không tĩnh trong lớp, vì không có đối tượng nào được tạo ra.
- Các khối tĩnh (static blocks) cũng có thể được sử dụng để khởi tạo các biến tĩnh khi lớp được tải.

## Ví dụ
### Ví dụ 1: Biến tĩnh
```java
class Counter {
    static int count = 0; // Biến tĩnh

    Counter() {
        count++;
    }

    static void displayCount() { // Phương thức tĩnh
        System.out.println("Số đối tượng đã được tạo: " + count);
    }
}

public class Test {
    public static void main(String[] args) {
        new Counter();
        new Counter();
        Counter.displayCount(); // Kết quả: Số đối tượng đã được tạo: 2
    }
}
```

### Ví dụ 2: Phương thức tĩnh
```java
class MathUtil {
    static int add(int a, int b) { // Phương thức tĩnh
        return a + b;
    }
}

public class Test {
    public static void main(String[] args) {
        int sum = MathUtil.add(5, 10); // Gọi phương thức tĩnh
        System.out.println("Tổng: " + sum); // Kết quả: Tổng: 15
    }
}
```

## Giải thích
- **Lỗi phổ biến**: Một trong những lỗi phổ biến khi sử dụng `static` là cố gắng truy cập vào các biến hoặc phương thức không tĩnh từ bên trong một phương thức tĩnh. Điều này sẽ dẫn đến lỗi biên dịch.
- **Khả năng mở rộng**: Việc sử dụng biến và phương thức tĩnh có thể làm giảm khả năng mở rộng của ứng dụng, vì tất cả các đối tượng chia sẻ cùng một biến tĩnh.
- **Thời gian sống**: Biến tĩnh tồn tại trong suốt thời gian chạy của chương trình, điều này có thể dẫn đến việc tiêu tốn bộ nhớ nếu không được quản lý tốt.

## Tóm tắt một câu
Từ khóa `static` trong Java cho phép khai báo các biến và phương thức tĩnh, có thể được sử dụng mà không cần khởi tạo một đối tượng của lớp, giúp tiết kiệm bộ nhớ và quản lý dữ liệu hiệu quả hơn.