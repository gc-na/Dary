<!--
Meta Description: # Lệnh "return" trong JAVA: Cách Sử Dụng và Ý Nghĩa ## Tóm Tắt Lệnh "return" trong JAVA được sử dụng để trả về giá trị từ một phương thức và ngắt quãn...
Meta Keywords: phương, thức, trả, giá, trị
-->

# Lệnh "return" trong JAVA: Cách Sử Dụng và Ý Nghĩa

## Tóm Tắt
Lệnh "return" trong JAVA được sử dụng để trả về giá trị từ một phương thức và ngắt quãng quá trình thực thi của phương thức đó.

## Tài Liệu
Lệnh "return" là một phần quan trọng trong ngôn ngữ lập trình JAVA, cho phép lập trình viên xác định giá trị mà một phương thức sẽ trả về cho nơi được gọi. Khi một phương thức được gọi, nó có thể thực hiện một số thao tác và cuối cùng "trả về" một giá trị, hoặc có thể không trả về giá trị nào (trong trường hợp phương thức đó có kiểu trả về là `void`).

### Cú pháp
```java
return [giá_trị];
```
- **giá_trị**: Là giá trị mà phương thức sẽ trả về. Nếu phương thức không trả về giá trị nào, bạn chỉ cần sử dụng `return;`.

### Mục Đích
- Ngắt quãng thực thi của phương thức và trả giá trị cho nơi gọi phương thức.
- Cung cấp giá trị kết quả cho các phép toán hoặc các xử lý tiếp theo.

## Ví Dụ
### Ví dụ 1: Phương thức trả về một số nguyên
```java
public class Demo {
    public static int tinhTong(int a, int b) {
        return a + b;
    }

    public static void main(String[] args) {
        int tong = tinhTong(5, 10);
        System.out.println("Tổng là: " + tong);
    }
}
```

### Ví dụ 2: Phương thức không trả về giá trị
```java
public class Demo {
    public static void inThongDiep() {
        System.out.println("Đây là một thông điệp.");
        return; // Có thể không cần thiết nhưng vẫn hợp lệ
    }

    public static void main(String[] args) {
        inThongDiep();
    }
}
```

## Giải Thích
Một số vấn đề thường gặp khi sử dụng lệnh "return":
- **Kiểu dữ liệu không khớp**: Khi bạn sử dụng "return", giá trị trả về phải khớp với kiểu dữ liệu đã định nghĩa của phương thức. Ví dụ, nếu phương thức có kiểu trả về là `int`, bạn không thể trả về một giá trị kiểu `String`.
- **Đặt lệnh return không đúng vị trí**: Nếu bạn đặt lệnh `return` trong một khối điều kiện mà không bao gồm tất cả các trường hợp, có thể xảy ra lỗi biên dịch. Đảm bảo rằng mọi đường đi trong phương thức đều có lệnh `return` nếu phương thức yêu cầu trả về giá trị.
- **Phương thức `void` không thể trả về giá trị**: Nếu phương thức được khai báo là `void`, bạn chỉ có thể sử dụng `return;` mà không cần giá trị nào đi kèm.

## Tóm Tắt Một Dòng
Lệnh "return" trong JAVA là công cụ cần thiết để trả về giá trị từ một phương thức và điều khiển luồng thực thi của chương trình.