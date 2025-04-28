<!--
Meta Description: # Câu lệnh "else" trong JAVA: Hướng dẫn chi tiết và ví dụ ## Tóm tắt Câu lệnh "else" trong JAVA là một phần của cấu trúc điều kiện, cho phép lập trình...
Meta Keywords: lệnh, câu, else, điều, kiện
-->

# Câu lệnh "else" trong JAVA: Hướng dẫn chi tiết và ví dụ

## Tóm tắt
Câu lệnh "else" trong JAVA là một phần của cấu trúc điều kiện, cho phép lập trình viên thực hiện các hành động khác nhau dựa vào điều kiện đã cho. Khi điều kiện của câu lệnh "if" không được thỏa mãn, câu lệnh "else" sẽ được thực thi.

## Tài liệu
Câu lệnh "else" trong JAVA thường được sử dụng kết hợp với câu lệnh "if" để kiểm soát luồng thực thi của chương trình. Cú pháp cơ bản của câu lệnh "else" như sau:

```java
if (điều kiện) {
    // Khối lệnh thực thi nếu điều kiện đúng
} else {
    // Khối lệnh thực thi nếu điều kiện sai
}
```

### Mục đích
Câu lệnh "else" giúp lập trình viên điều hướng các tình huống khác nhau trong mã nguồn. Nó là công cụ quan trọng để xử lý các quyết định trong chương trình.

### Cách sử dụng
- Câu lệnh "else" thường đi kèm với câu lệnh "if".
- Có thể kết hợp nhiều câu lệnh "else if" để kiểm tra nhiều điều kiện khác nhau.

## Ví dụ
Dưới đây là một số ví dụ đơn giản về việc sử dụng câu lệnh "else":

### Ví dụ 1: Kiểm tra số chẵn lẻ

```java
public class CheckEvenOdd {
    public static void main(String[] args) {
        int number = 10;
        
        if (number % 2 == 0) {
            System.out.println("Số là chẵn.");
        } else {
            System.out.println("Số là lẻ.");
        }
    }
}
```

### Ví dụ 2: Kiểm tra điểm số

```java
public class GradeCheck {
    public static void main(String[] args) {
        int score = 75;
        
        if (score >= 60) {
            System.out.println("Bạn đã đậu.");
        } else {
            System.out.println("Bạn đã rớt.");
        }
    }
}
```

## Giải thích
### Những điều cần lưu ý:
- Câu lệnh "else" phải luôn đi sau câu lệnh "if" và không thể đứng một mình.
- Trong trường hợp không có câu lệnh "else", chương trình sẽ không thực hiện gì nếu điều kiện không thỏa mãn.
- Có thể có nhiều câu lệnh "else if" để kiểm tra nhiều điều kiện khác nhau.

### Những lỗi thường gặp:
- Bỏ qua cặp dấu ngoặc nhọn `{}` khi chỉ có một câu lệnh trong khối "if" hoặc "else". Mặc dù không bắt buộc, việc sử dụng chúng giúp cải thiện tính rõ ràng và dễ bảo trì của mã nguồn.

## Tóm tắt một dòng
Câu lệnh "else" trong JAVA cho phép lập trình viên xác định hành động thực hiện khi điều kiện của câu lệnh "if" không được thỏa mãn.