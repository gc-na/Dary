<!--
Meta Description: # Float trong Java: Kiểu dữ liệu số thực ## Tóm tắt Trong Java, `float` là một kiểu dữ liệu số thực, cho phép lưu trữ các giá trị số với độ chính xác ...
Meta Keywords: float, các, phép, java, kiểu
-->

# Float trong Java: Kiểu dữ liệu số thực

## Tóm tắt
Trong Java, `float` là một kiểu dữ liệu số thực, cho phép lưu trữ các giá trị số với độ chính xác đơn. `float` thường được sử dụng khi cần tiết kiệm bộ nhớ cho các phép toán số học không yêu cầu độ chính xác cao.

## Tài liệu
### Mục đích
Kiểu dữ liệu `float` trong Java được sử dụng để biểu diễn các số thực với độ chính xác đơn, chiếm 4 byte (32 bit) trong bộ nhớ. `float` có khả năng lưu trữ các giá trị từ khoảng -3.40282347E+38 đến 3.40282347E+38. 

### Cách sử dụng
Để khai báo một biến kiểu `float`, bạn cần sử dụng từ khóa `float` và thêm hậu tố `f` hoặc `F` cho giá trị số thực. Ví dụ:

```java
float myFloat = 5.75f;
```

Nếu không sử dụng hậu tố `f`, Java sẽ coi nó là kiểu `double` mặc định và sẽ gây lỗi biên dịch.

### Chi tiết
- Để thực hiện các phép toán với biến `float`, bạn có thể sử dụng các toán tử số học như `+`, `-`, `*`, `/`.
- Khi thực hiện các phép toán giữa các kiểu dữ liệu khác nhau, Java sẽ tự động chuyển đổi kiểu (implicit casting) nếu cần thiết.
- Cần lưu ý rằng việc sử dụng `float` có thể dẫn đến sai số do cách lưu trữ số thực trong bộ nhớ máy tính.

## Ví dụ
### Khai báo và khởi tạo biến float
```java
public class FloatExample {
    public static void main(String[] args) {
        float a = 10.5f;
        float b = 3.2f;
        float sum = a + b;

        System.out.println("Tổng: " + sum); // In ra: Tổng: 13.7
    }
}
```

### Phép toán với biến float
```java
public class FloatOperations {
    public static void main(String[] args) {
        float x = 5.0f;
        float y = 2.0f;

        float addition = x + y; // Phép cộng
        float subtraction = x - y; // Phép trừ
        float multiplication = x * y; // Phép nhân
        float division = x / y; // Phép chia

        System.out.println("Cộng: " + addition); // In ra: Cộng: 7.0
        System.out.println("Trừ: " + subtraction); // In ra: Trừ: 3.0
        System.out.println("Nhân: " + multiplication); // In ra: Nhân: 10.0
        System.out.println("Chia: " + division); // In ra: Chia: 2.5
    }
}
```

## Giải thích
- **Sai số chính xác**: Do đặc tính lưu trữ của kiểu số thực, các phép toán với `float` có thể dẫn đến các sai số nhỏ. Ví dụ, phép cộng hoặc trừ các số rất lớn và rất nhỏ có thể cho kết quả không chính xác.
- **So sánh số**: Khi so sánh các giá trị `float`, luôn cẩn thận với sai số có thể xảy ra. Thay vì so sánh trực tiếp, hãy sử dụng một ngưỡng (threshold) để kiểm tra sự gần đúng.

## Tóm tắt một dòng
`float` trong Java là kiểu dữ liệu số thực với độ chính xác đơn, thích hợp cho các phép toán không yêu cầu độ chính xác cao và tiết kiệm bộ nhớ.