<!--
Meta Description: # Sử Dụng Câu Lệnh "assert" Trong Java: Kiểm Tra Điều Kiện ## Tóm tắt Câu lệnh `assert` trong Java được sử dụng để kiểm tra các điều kiện trong mã ngu...
Meta Keywords: trong, assert, điều, lệnh, kiện
-->

# Sử Dụng Câu Lệnh "assert" Trong Java: Kiểm Tra Điều Kiện

## Tóm tắt
Câu lệnh `assert` trong Java được sử dụng để kiểm tra các điều kiện trong mã nguồn, giúp phát hiện lỗi trong quá trình phát triển phần mềm. Nó cho phép lập trình viên xác minh rằng một điều kiện nào đó là đúng và sẽ thông báo nếu điều kiện đó sai.

## Tài liệu
Câu lệnh `assert` là một phần của Java từ phiên bản 1.4. Mục đích chính của nó là cung cấp một cơ chế kiểm tra điều kiện trong mã mà không cần phải sử dụng các câu lệnh kiểm tra lỗi phức tạp. Khi bạn viết mã, bạn có thể sử dụng `assert` để đảm bảo rằng các giả định của bạn về trạng thái chương trình là đúng trong khi phát triển.

### Cú pháp
```java
assert condition;
assert condition : message;
```

- `condition`: Biểu thức phải trả về giá trị boolean. Nếu điều kiện là `false`, một ngoại lệ `AssertionError` sẽ được ném ra.
- `message`: Một thông điệp tùy chọn mà bạn có thể cung cấp để mô tả lý do tại sao điều kiện bị lỗi.

### Kích hoạt câu lệnh assert
Mặc định, các câu lệnh `assert` bị tắt trong Java. Để kích hoạt chúng, bạn cần sử dụng tham số `-ea` (hoặc `-enableassertions`) khi chạy chương trình. Ví dụ:
```bash
java -ea MyClass
```

## Ví dụ
### Ví dụ Cơ Bản
```java
public class AssertExample {
    public static void main(String[] args) {
        int x = 5;
        assert x > 0 : "x phải lớn hơn 0";
        System.out.println("Giá trị của x là: " + x);
    }
}
```
Trong ví dụ trên, nếu `x` không lớn hơn 0, chương trình sẽ ném ra một `AssertionError` với thông điệp "x phải lớn hơn 0".

### Ví dụ Nâng Cao
```java
public class MathUtils {
    public static int divide(int a, int b) {
        assert b != 0 : "Mẫu số không được bằng 0";
        return a / b;
    }

    public static void main(String[] args) {
        System.out.println(divide(10, 2)); // Kết quả: 5
        System.out.println(divide(10, 0)); // Ném ra AssertionError
    }
}
```
Trong ví dụ này, nếu bạn cố gắng chia cho 0, chương trình sẽ ném ra một `AssertionError` với thông điệp "Mẫu số không được bằng 0".

## Giải thích
Các câu lệnh `assert` rất hữu ích trong quá trình phát triển phần mềm, nhưng có một số điều cần lưu ý:
- **Không nên sử dụng cho kiểm tra đầu vào**: Vì câu lệnh `assert` có thể bị tắt trong môi trường sản xuất, bạn không nên dùng nó để kiểm tra các điều kiện đầu vào của người dùng.
- **Hiệu suất**: Khi `assert` bị tắt, mã lệnh sẽ không được thực thi, giúp nâng cao hiệu suất của ứng dụng.
- **Thời gian chạy**: Câu lệnh `assert` chỉ nên được sử dụng để kiểm tra các điều kiện mà bạn tin tưởng là đúng trong quá trình phát triển. Nếu điều kiện có thể sai trong môi trường sản xuất, hãy sử dụng các phương pháp kiểm tra khác.

## Tóm tắt một dòng
Câu lệnh `assert` trong Java cho phép lập trình viên kiểm tra các điều kiện trong mã nguồn, giúp phát hiện lỗi và đảm bảo tính đúng đắn của chương trình trong quá trình phát triển.