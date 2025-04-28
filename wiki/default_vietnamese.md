<!--
Meta Description: # Từ Khóa "default" Trong JAVA: Hiểu Biết Cần Thiết ## Tóm Tắt Trong JAVA, từ khóa "default" được sử dụng để chỉ định các phương thức mặc định trong c...
Meta Keywords: định, phương, thức, mặc, cần
-->

# Từ Khóa "default" Trong JAVA: Hiểu Biết Cần Thiết

## Tóm Tắt
Trong JAVA, từ khóa "default" được sử dụng để chỉ định các phương thức mặc định trong các interface, cho phép định nghĩa các hành vi mặc định mà không cần phải triển khai lại trong các lớp con. Điều này giúp tăng tính linh hoạt và giảm thiểu mã lặp lại.

## Tài Liệu
Từ khóa "default" được giới thiệu trong JAVA 8 như một phần của tính năng mới cho phép các interface có thể có phương thức với thân hàm. Mục đích chính của việc sử dụng "default" là để cung cấp các phương thức mặc định mà các lớp triển khai có thể sử dụng trực tiếp mà không cần phải cài đặt lại.

### Cách Sử Dụng
Để định nghĩa một phương thức mặc định trong một interface, bạn sử dụng từ khóa "default" trước khai báo phương thức. Dưới đây là cú pháp chung:

```java
public interface TênInterface {
    default kiểuTrảVề tênPhươngThức() {
        // Thân hàm
    }
}
```

Khi một lớp thực hiện interface này, nó có thể sử dụng phương thức mặc định mà không cần phải triển khai, hoặc có thể ghi đè nếu cần.

## Ví Dụ
Dưới đây là một ví dụ minh họa về cách sử dụng từ khóa "default" trong JAVA:

```java
interface Hinh {
    default void hienThi() {
        System.out.println("Đây là hình.");
    }
}

class HinhVuong implements Hinh {
    // Không cần phải định nghĩa lại phương thức hienThi()
}

public class Main {
    public static void main(String[] args) {
        HinhVuong hv = new HinhVuong();
        hv.hienThi(); // Kết quả: Đây là hình.
    }
}
```

Trong ví dụ trên, lớp `HinhVuong` sử dụng phương thức mặc định `hienThi()` từ interface `Hinh` mà không cần định nghĩa lại.

## Giải Thích
Mặc dù việc sử dụng từ khóa "default" mang lại nhiều lợi ích, có một số vấn đề và lưu ý cần cân nhắc:

1. **Ghi Đè Phương Thức**: Nếu lớp con cần một hành vi khác, nó có thể ghi đè phương thức mặc định, nhưng cần chú ý rằng việc ghi đè phương thức có cùng tên từ nhiều interface có thể gây ra xung đột.

2. **Tính Tương Thích**: Việc thêm phương thức mặc định vào interface có thể gây ra vấn đề tương thích với các lớp cũ đã triển khai interface này trước khi có phương thức mặc định.

3. **Sử Dụng Thận Trọng**: Cần phải cân nhắc kỹ lưỡng khi sử dụng phương thức mặc định để tránh làm phức tạp hóa mã nguồn và giảm tính rõ ràng.

## Tóm Tắt Một Câu
Từ khóa "default" trong JAVA cho phép các phương thức mặc định trong interface, tăng tính linh hoạt và giảm mã lặp lại cho các lớp triển khai.