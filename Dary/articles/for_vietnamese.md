<!--
Meta Description: # Cấu trúc Lặp "for" trong Java: Hướng Dẫn Chi Tiết ## Tóm tắt Cấu trúc lặp "for" trong Java là một công cụ mạnh mẽ cho phép lập trình viên thực hiện ...
Meta Keywords: lặp, điều, kiện, cấu, trúc
-->

# Cấu trúc Lặp "for" trong Java: Hướng Dẫn Chi Tiết

## Tóm tắt
Cấu trúc lặp "for" trong Java là một công cụ mạnh mẽ cho phép lập trình viên thực hiện một đoạn mã nhiều lần với điều kiện cụ thể. Đây là một trong những cấu trúc lặp phổ biến nhất, thường được sử dụng để duyệt qua các mảng và tập hợp.

## Tài liệu
Cấu trúc lặp "for" được sử dụng để lặp qua một dãy số hoặc một tập hợp các phần tử. Cú pháp cơ bản của câu lệnh "for" trong Java như sau:

```java
for (khởi_tạo; điều_kiện; cập_nhật) {
    // đoạn mã cần thực thi
}
```

### Mục đích
- **Khởi tạo**: Thiết lập biến điều kiện trước khi bắt đầu vòng lặp.
- **Điều kiện**: Biểu thức boolean kiểm tra trước mỗi lần lặp. Nếu điều kiện đúng, vòng lặp sẽ tiếp tục; nếu sai, vòng lặp sẽ dừng lại.
- **Cập nhật**: Cập nhật giá trị của biến điều kiện sau mỗi lần lặp.

### Sử dụng
Cấu trúc lặp "for" rất hữu ích trong nhiều tình huống, đặc biệt khi bạn biết trước số lần lặp. Nó thường được sử dụng để duyệt qua các mảng hoặc danh sách, hoặc khi thực hiện các phép toán lặp lại.

## Ví dụ
### Ví dụ Cơ Bản
```java
public class ForLoopExample {
    public static void main(String[] args) {
        // In ra số từ 0 đến 4
        for (int i = 0; i < 5; i++) {
            System.out.println(i);
        }
    }
}
```

### Ví dụ Duyệt Qua Mảng
```java
public class ArrayLoopExample {
    public static void main(String[] args) {
        int[] numbers = {10, 20, 30, 40, 50};
        for (int i = 0; i < numbers.length; i++) {
            System.out.println(numbers[i]);
        }
    }
}
```

## Giải thích
### Những Lỗi Thường Gặp
- **Quên Cập Nhật Biến**: Nếu không cập nhật biến điều kiện, vòng lặp sẽ trở thành vòng lặp vô hạn.
- **Điều Kiện Sai**: Nếu điều kiện không được thiết lập chính xác, vòng lặp có thể không chạy hoặc chạy không theo ý muốn.

### Lưu Ý
- Cấu trúc lặp "for" có thể được kết hợp với nhiều kiểu dữ liệu khác nhau và có thể được sử dụng trong các cấu trúc lặp khác như "while" và "do-while".
- Java cũng hỗ trợ vòng lặp "enhanced for" (hay còn gọi là for-each) dành riêng cho việc duyệt qua các mảng và tập hợp.

## Tóm tắt Một Dòng
Cấu trúc lặp "for" trong Java là một công cụ hiệu quả để thực hiện các phép lặp có điều kiện, thường được sử dụng trong các tình huống lặp qua mảng và danh sách.