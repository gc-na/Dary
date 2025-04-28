<!--
Meta Description: # Câu lệnh "do" trong Java: Cách sử dụng và ví dụ ## Tóm tắt Câu lệnh `do` trong Java được sử dụng để thực hiện một khối mã lặp lại ít nhất một lần tr...
Meta Keywords: một, câu, lệnh, điều, trong
-->

# Câu lệnh "do" trong Java: Cách sử dụng và ví dụ

## Tóm tắt
Câu lệnh `do` trong Java được sử dụng để thực hiện một khối mã lặp lại ít nhất một lần trước khi kiểm tra điều kiện. Câu lệnh này là một phần của cấu trúc lặp `do-while`, cho phép lập trình viên dễ dàng viết mã lặp.

## Tài liệu
Câu lệnh `do` trong Java là một phần của cấu trúc lặp `do-while`, cho phép thực hiện một khối mã cho đến khi một điều kiện nhất định được kiểm tra và trở thành sai. Cú pháp của câu lệnh này như sau:

```java
do {
    // Khối mã sẽ được thực thi
} while (điều kiện);
```

**Mục đích**: Câu lệnh `do` đảm bảo rằng khối mã bên trong luôn được thực thi ít nhất một lần, bất kể điều kiện ban đầu là đúng hay sai.

**Cách sử dụng**:
- **Khởi tạo**: Đầu tiên, bạn cần khởi tạo bất kỳ biến nào cần thiết cho điều kiện.
- **Khối mã**: Viết mã cần thực thi bên trong dấu ngoặc nhọn `{}`.
- **Điều kiện**: Cuối cùng, chỉ định điều kiện để tiếp tục lặp lại khối mã.

## Ví dụ
Dưới đây là một số ví dụ đơn giản về cách sử dụng câu lệnh `do` trong Java:

### Ví dụ 1: Đếm từ 1 đến 5
```java
public class Main {
    public static void main(String[] args) {
        int i = 1;

        do {
            System.out.println(i);
            i++;
        } while (i <= 5);
    }
}
```
Kết quả:
```
1
2
3
4
5
```

### Ví dụ 2: Yêu cầu người dùng nhập vào số
```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int number;

        do {
            System.out.print("Nhập một số (0 để thoát): ");
            number = scanner.nextInt();
        } while (number != 0);

        System.out.println("Chương trình kết thúc.");
    }
}
```

## Giải thích
Một số điểm cần lưu ý khi sử dụng câu lệnh `do` trong Java:
- **Thực thi tối thiểu một lần**: Khác với câu lệnh `while`, câu lệnh `do` đảm bảo rằng khối mã sẽ được thực thi ít nhất một lần, ngay cả khi điều kiện ban đầu là sai.
- **Cấu trúc lặp không bao giờ kết thúc**: Nếu điều kiện trong câu lệnh `do-while` luôn đúng, chương trình sẽ rơi vào vòng lặp vô hạn, điều này có thể gây ra sự cố cho ứng dụng.
- **Sử dụng biến đúng cách**: Đảm bảo rằng các biến được sử dụng trong điều kiện đã được khởi tạo và cập nhật đúng cách trong khối mã lặp.

## Tóm tắt một dòng
Câu lệnh `do` trong Java cho phép thực hiện một khối mã ít nhất một lần trước khi kiểm tra điều kiện, là một công cụ hữu ích cho việc lập trình lặp.