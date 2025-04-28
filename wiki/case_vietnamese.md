<!--
Meta Description: # Câu lệnh "case" trong Java: Hướng dẫn Chi tiết và Ví dụ Cụ thể ## Tóm tắt Câu lệnh "case" trong Java là một phần của cấu trúc điều kiện switch, cho ...
Meta Keywords: case, break, câu, lệnh, switch
-->

# Câu lệnh "case" trong Java: Hướng dẫn Chi tiết và Ví dụ Cụ thể

## Tóm tắt
Câu lệnh "case" trong Java là một phần của cấu trúc điều kiện switch, cho phép lập trình viên kiểm tra một biến với nhiều giá trị khác nhau và thực hiện các hành động tương ứng.

## Tài liệu
Câu lệnh "case" được sử dụng trong cấu trúc điều kiện `switch`, giúp xử lý nhiều điều kiện mà không cần phải sử dụng nhiều câu lệnh `if-else`. Cấu trúc cơ bản của câu lệnh `switch` bao gồm một biểu thức, theo sau là một hoặc nhiều câu lệnh `case` để kiểm tra các giá trị cụ thể.

### Cú pháp:
```java
switch (biểu_thức) {
    case giá_trị_1:
        // thực hiện hành động cho giá trị 1
        break;
    case giá_trị_2:
        // thực hiện hành động cho giá trị 2
        break;
    // ...
    default:
        // thực hiện hành động mặc định nếu không có giá trị nào khớp
}
```

### Mục đích:
- Giúp đơn giản hóa mã nguồn khi cần kiểm tra nhiều giá trị khác nhau.
- Tăng khả năng đọc mã và giảm số lượng câu lệnh điều kiện lồng nhau.

### Sử dụng:
- `switch` có thể sử dụng với các kiểu dữ liệu nguyên thủy như `int`, `char`, và `enum`, cũng như kiểu `String` trong Java 7 trở đi.
- Mỗi khối `case` nên kết thúc bằng câu lệnh `break` để ngăn việc thực thi các khối `case` tiếp theo.

## Ví dụ
```java
int ngay = 3;
String tenNgay;

switch (ngay) {
    case 1:
        tenNgay = "Thứ Hai";
        break;
    case 2:
        tenNgay = "Thứ Ba";
        break;
    case 3:
        tenNgay = "Thứ Tư";
        break;
    case 4:
        tenNgay = "Thứ Năm";
        break;
    case 5:
        tenNgay = "Thứ Sáu";
        break;
    case 6:
        tenNgay = "Thứ Bảy";
        break;
    case 7:
        tenNgay = "Chủ Nhật";
        break;
    default:
        tenNgay = "Không hợp lệ";
}

System.out.println(tenNgay); // Kết quả: Thứ Tư
```

## Giải thích
- **Câu lệnh `break`**: Nếu quên câu lệnh `break`, chương trình sẽ tiếp tục thực hiện các khối `case` tiếp theo cho đến khi gặp `break` hoặc kết thúc `switch`, điều này có thể dẫn đến kết quả không mong muốn.
- **Giá trị trùng lặp**: Không nên có hai hoặc nhiều khối `case` với cùng một giá trị, điều này sẽ gây lỗi biên dịch.
- **Biểu thức `switch`**: Biểu thức trong `switch` chỉ có thể là các kiểu dữ liệu nguyên thủy và `String` (từ Java 7 trở đi). Không thể sử dụng các kiểu dữ liệu phức tạp như `float` hoặc `double`.

## Tóm tắt một dòng
Câu lệnh "case" trong Java cho phép kiểm tra nhiều giá trị khác nhau của một biến trong cấu trúc điều kiện `switch`, giúp giảm độ phức tạp của mã nguồn.