<!--
Meta Description: # Câu Lệnh "if" trong Java: Cách Sử Dụng và Ví Dụ ## Tóm Tắt Câu lệnh "if" trong Java là một cấu trúc điều kiện cho phép thực hiện các khối mã khác nh...
Meta Keywords: điều, câu, lệnh, kiện, trong
-->

# Câu Lệnh "if" trong Java: Cách Sử Dụng và Ví Dụ

## Tóm Tắt
Câu lệnh "if" trong Java là một cấu trúc điều kiện cho phép thực hiện các khối mã khác nhau dựa trên điều kiện được kiểm tra. Đây là một trong những cấu trúc lập trình cơ bản và quan trọng nhất trong Java.

## Tài Liệu
Câu lệnh "if" trong Java được sử dụng để kiểm tra một điều kiện boolean. Nếu điều kiện là đúng (true), khối mã bên trong câu lệnh "if" sẽ được thực thi. Câu lệnh này giúp lập trình viên điều khiển luồng thực thi của chương trình dựa trên các điều kiện xác định.

### Cú Pháp
```java
if (điều_kiện) {
    // Khối mã thực thi nếu điều kiện đúng
}
```

Có thể mở rộng câu lệnh "if" với các câu lệnh "else" và "else if" để kiểm tra nhiều điều kiện khác nhau:
```java
if (điều_kiện1) {
    // Khối mã thực thi nếu điều kiện1 đúng
} else if (điều_kiện2) {
    // Khối mã thực thi nếu điều kiện2 đúng
} else {
    // Khối mã thực thi nếu không có điều kiện nào đúng
}
```

## Ví Dụ
### Ví Dụ Cơ Bản
```java
int a = 10;
if (a > 5) {
    System.out.println("a lớn hơn 5");
}
```

### Ví Dụ với "else if" và "else"
```java
int b = 10;

if (b < 5) {
    System.out.println("b nhỏ hơn 5");
} else if (b == 5) {
    System.out.println("b bằng 5");
} else {
    System.out.println("b lớn hơn 5");
}
```

## Giải Thích
Một số điểm cần lưu ý khi sử dụng câu lệnh "if":
- **Kiểu Dữ Liệu**: Điều kiện trong câu lệnh "if" phải trả về kiểu boolean. Nếu không, sẽ xảy ra lỗi biên dịch.
- **Khối Mã**: Cần phải sử dụng dấu ngoặc nhọn `{}` để bao quanh nhiều câu lệnh trong khối mã. Nếu chỉ có một câu lệnh, dấu ngoặc nhọn có thể được bỏ qua.
- **Biểu Thức Boolean**: Các biểu thức boolean có thể bao gồm các phép so sánh như `==`, `!=`, `<`, `>`, `<=`, `>=`.
- **Phép Toán Logic**: Có thể kết hợp nhiều điều kiện với nhau bằng cách sử dụng các phép toán logic như `&&` (và) và `||` (hoặc).

## Tóm Tắt Một Dòng
Câu lệnh "if" trong Java cho phép kiểm tra điều kiện và điều khiển luồng thực thi của chương trình dựa trên kết quả của điều kiện đó.