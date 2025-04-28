<!--
Meta Description: # Từ Khóa: Sealed Class trong Java: Chức Năng, Cách Sử Dụng và Ví Dụ ## Tóm Tắt Sealed class trong Java là một tính năng được giới thiệu trong Java 15...
Meta Keywords: lớp, sealed, class, trong, một
-->

# Từ Khóa: Sealed Class trong Java: Chức Năng, Cách Sử Dụng và Ví Dụ

## Tóm Tắt
Sealed class trong Java là một tính năng được giới thiệu trong Java 15, cho phép lập trình viên kiểm soát các lớp có thể kế thừa từ một lớp cụ thể. Điều này giúp tăng cường tính an toàn và dễ bảo trì của mã nguồn.

## Tài Liệu
### Mục Đích
Sealed class được thiết kế để giới hạn việc kế thừa trong một số lớp nhất định. Bằng cách này, lập trình viên có thể định nghĩa một hierachy lớp rõ ràng, đảm bảo rằng chỉ những lớp đã được chỉ định mới có thể mở rộng một lớp cha nhất định.

### Cách Sử Dụng
Để khai báo một sealed class, bạn sử dụng từ khóa `sealed` trước định nghĩa lớp. Các lớp con có thể được chỉ định bằng cách sử dụng các từ khóa `non-sealed`, `final`, hoặc `sealed`.

Cú pháp cơ bản để khai báo một sealed class như sau:

```java
public sealed class Animal permits Dog, Cat {
    // Nội dung của lớp
}

public final class Dog extends Animal {
    // Nội dung của lớp Dog
}

public final class Cat extends Animal {
    // Nội dung của lớp Cat
}
```

### Chi Tiết
- **sealed**: Từ khóa này chỉ ra rằng lớp không thể được kế thừa bởi bất kỳ lớp nào trừ khi được chỉ định trong danh sách `permits`.
- **permits**: Đây là từ khóa theo sau sealed class, nó xác định các lớp cụ thể có thể kế thừa từ sealed class.
- **final**: Lớp được định nghĩa là final không thể được kế thừa nữa.
- **non-sealed**: Nếu một lớp con được đánh dấu là non-sealed, nó có thể được kế thừa bởi bất kỳ lớp nào.

## Ví Dụ
Dưới đây là một ví dụ đơn giản về sealed class:

```java
public sealed class Shape permits Circle, Rectangle {
    // Phương thức và thuộc tính của lớp Shape
}

public final class Circle extends Shape {
    // Phương thức và thuộc tính của lớp Circle
}

public final class Rectangle extends Shape {
    // Phương thức và thuộc tính của lớp Rectangle
}
```

Trong ví dụ này, lớp `Shape` là sealed và chỉ các lớp `Circle` và `Rectangle` có thể kế thừa từ nó.

## Giải Thích
### Những Lỗi Thường Gặp
- **Quên chỉ định lớp trong `permits`**: Nếu bạn không chỉ định các lớp con trong danh sách permits, trình biên dịch sẽ báo lỗi.
- **Kế thừa từ sealed class mà không có quyền**: Nếu bạn cố gắng tạo một lớp con từ sealed class không nằm trong danh sách permits, bạn sẽ nhận được lỗi biên dịch.

### Lưu Ý
Sealed class rất hữu ích trong việc xây dựng các hệ thống phức tạp, nơi mà sự rõ ràng và an toàn trong kế thừa là rất quan trọng. Hãy sử dụng chúng cẩn thận để tránh làm phức tạp cấu trúc lớp của bạn.

## Tóm Tắt Một Dòng
Sealed class trong Java cho phép lập trình viên kiểm soát các lớp có thể kế thừa từ một lớp cha, tăng cường tính an toàn và khả năng bảo trì của mã nguồn.