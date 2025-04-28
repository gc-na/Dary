<!--
Meta Description: # Câu lệnh Switch trong JAVA: Hướng Dẫn Chi Tiết và Ví Dụ Cụ Thể ## Tóm Tắt Câu lệnh `switch` trong JAVA cho phép lập trình viên thực hiện các nhánh đ...
Meta Keywords: switch, case, câu, lệnh, một
-->

# Câu lệnh Switch trong JAVA: Hướng Dẫn Chi Tiết và Ví Dụ Cụ Thể

## Tóm Tắt
Câu lệnh `switch` trong JAVA cho phép lập trình viên thực hiện các nhánh điều kiện khác nhau dựa trên giá trị của một biến. Đây là một công cụ hữu ích giúp mã nguồn trở nên gọn gàng và dễ đọc hơn so với nhiều câu lệnh `if-else`.

## Tài Liệu
Câu lệnh `switch` được sử dụng để kiểm tra giá trị của một biến và thực hiện các khối mã khác nhau dựa trên giá trị đó. Cú pháp cơ bản của câu lệnh `switch` như sau:

```java
switch (biến) {
    case giá_trị_1:
        // Mã thực thi nếu biến bằng giá_trị_1
        break;
    case giá_trị_2:
        // Mã thực thi nếu biến bằng giá_trị_2
        break;
    // Có thể có nhiều case
    default:
        // Mã thực thi nếu không có case nào khớp
}
```

### Mục Đích
Câu lệnh `switch` giúp tăng tính rõ ràng trong mã nguồn và dễ dàng quản lý các nhánh điều kiện. Nó hỗ trợ các kiểu dữ liệu như `int`, `char`, `String`, và một số kiểu dữ liệu khác.

### Sử Dụng
- **Khi nào nên sử dụng**: Sử dụng câu lệnh `switch` khi bạn cần kiểm tra nhiều giá trị khác nhau cho cùng một biến.
- **Khi nào không nên sử dụng**: Nếu chỉ có hai điều kiện, câu lệnh `if-else` có thể là sự lựa chọn tốt hơn.

## Ví Dụ
### Ví dụ Cơ Bản 1: Sử Dụng với Số Nguyên
```java
int day = 3;
String dayName;

switch (day) {
    case 1:
        dayName = "Chủ Nhật";
        break;
    case 2:
        dayName = "Thứ Hai";
        break;
    case 3:
        dayName = "Thứ Ba";
        break;
    default:
        dayName = "Ngày không hợp lệ";
}

System.out.println(dayName); // Kết quả: Thứ Ba
```

### Ví dụ Cơ Bản 2: Sử Dụng với Chuỗi
```java
String fruit = "Táo";

switch (fruit) {
    case "Chuối":
        System.out.println("Chuối là một loại trái cây tốt.");
        break;
    case "Táo":
        System.out.println("Táo rất ngon.");
        break;
    default:
        System.out.println("Trái cây không xác định.");
}

// Kết quả: Táo rất ngon.
```

## Giải Thích
### Những Lưu Ý Thông Thường
1. **Thiếu `break`**: Nếu không sử dụng từ khóa `break`, chương trình sẽ tiếp tục thực hiện các case phía dưới, điều này có thể dẫn đến kết quả không mong muốn.
2. **Giá trị không khớp**: Nếu không có case nào khớp với giá trị của biến, khối mã trong `default` sẽ được thực hiện (nếu có).
3. **Kiểu Dữ Liệu**: Câu lệnh `switch` có thể sử dụng trên các kiểu dữ liệu nguyên thủy (như `int`, `char`) và kiểu đối tượng như `String`.

## Tóm Tắt Một Dòng
Câu lệnh `switch` trong JAVA cho phép lập trình viên xử lý nhiều nhánh điều kiện một cách hiệu quả dựa trên giá trị của một biến.