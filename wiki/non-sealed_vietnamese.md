<!--
Meta Description: # Non-Sealed trong Java: Hiểu Biết và Ứng Dụng ## Tóm tắt Non-sealed là một từ khóa trong Java, được giới thiệu từ phiên bản Java 17, cho phép lập trì...
Meta Keywords: lớp, sealed, non, các, thừa
-->

# Non-Sealed trong Java: Hiểu Biết và Ứng Dụng

## Tóm tắt
Non-sealed là một từ khóa trong Java, được giới thiệu từ phiên bản Java 17, cho phép lập trình viên chỉ định rằng một lớp không thể bị kế thừa bởi các lớp khác, dù cho các lớp con có thể được định nghĩa. Tính năng này giúp tăng cường kiểm soát trong lập trình hướng đối tượng, đặc biệt trong việc quản lý các lớp dữ liệu.

## Tài liệu
### Mục đích
Từ khóa non-sealed được sử dụng để chỉ định rằng một lớp có thể được kế thừa, nhưng không cho phép bất kỳ lớp nào khác kế thừa từ lớp kế thừa của lớp đó. Điều này giúp lập trình viên bảo vệ cấu trúc của ứng dụng và giảm thiểu sự phức tạp trong việc quản lý các lớp con.

### Cách sử dụng
Để sử dụng non-sealed, bạn chỉ cần thêm từ khóa "non-sealed" trước định nghĩa lớp con. Dưới đây là cú pháp cơ bản:

```java
non-sealed class TenLopKeThua extends TenLopCha {
    // Thực hiện các phương thức và thuộc tính của lớp
}
```

### Chi tiết
Khi một lớp được đánh dấu là non-sealed, nó có thể được kế thừa bởi các lớp con, nhưng các lớp con đó không thể được kế thừa nữa. Điều này rất hữu ích khi bạn muốn hạn chế việc mở rộng thêm mà không cần phải khóa hoàn toàn lớp của bạn như một lớp sealed.

## Ví dụ
Dưới đây là một ví dụ đơn giản về cách sử dụng non-sealed trong Java:

```java
sealed class Vehicle permits Car, Truck {
    // Các thuộc tính và phương thức chung cho các phương tiện
}

non-sealed class Car extends Vehicle {
    // Các thuộc tính và phương thức cho xe hơi
}

class SportsCar extends Car {
    // Các thuộc tính và phương thức cho xe thể thao
}

non-sealed class Truck extends Vehicle {
    // Các thuộc tính và phương thức cho xe tải
}
```

Trong ví dụ này, `Vehicle` là một lớp sealed cho phép `Car` và `Truck` kế thừa. Lớp `Car` được đánh dấu là non-sealed, cho phép lớp `SportsCar` kế thừa từ nó, trong khi `Truck` cũng có thể được mở rộng với những lớp khác.

## Giải thích
Một số điểm cần lưu ý khi sử dụng non-sealed:
- **Quản lý kế thừa**: Khi sử dụng non-sealed, hãy chắc chắn rằng bạn hiểu rõ cấu trúc lớp và cách mà các lớp sẽ được kế thừa. Sự phức tạp có thể gia tăng nếu bạn không quản lý đúng cách.
- **Khả năng bảo trì**: Đánh dấu một lớp là non-sealed có thể ảnh hưởng đến khả năng bảo trì của mã. Hãy cân nhắc kỹ lưỡng trước khi quyết định sử dụng tính năng này.
- **Tương thích với các phiên bản cũ**: Non-sealed chỉ khả dụng từ Java 17 trở đi, vì vậy hãy đảm bảo rằng môi trường phát triển của bạn tương thích với phiên bản này.

## Tóm tắt một dòng
Non-sealed trong Java cho phép lớp con được kế thừa nhưng ngăn không cho các lớp khác kế thừa từ lớp con đó, mang lại sự kiểm soát tốt hơn trong lập trình hướng đối tượng.