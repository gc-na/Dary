<!--
Meta Description: # Từ Khóa: Sử Dụng Từ Khóa "yield" Trong Java: Hướng Dẫn Chi Tiết ## Tóm Tắt Từ khóa "yield" trong Java được giới thiệu trong phiên bản Java 14 như mộ...
Meta Keywords: trong, yield, dụng, các, luồng
-->

# Từ Khóa: Sử Dụng Từ Khóa "yield" Trong Java: Hướng Dẫn Chi Tiết

## Tóm Tắt
Từ khóa "yield" trong Java được giới thiệu trong phiên bản Java 14 như một phần của tính năng "record" và trong ngữ cảnh của các biểu thức lambda. Nó cho phép tạm dừng một luồng (thread) và trả về giá trị trong một phương thức.

## Tài Liệu
### Mục Đích
Từ khóa "yield" được sử dụng để tạm dừng một luồng, cho phép các luồng khác được thực thi trong khi vẫn giữ trạng thái của luồng hiện tại, giống như việc sử dụng từ khóa "return" nhưng với khả năng cho phép luồng khác có thời gian chạy.

### Cách Sử Dụng
Kể từ Java 14, "yield" có thể được sử dụng trong ngữ cảnh của biểu thức lambda và trong các phương thức của các lớp record. Cú pháp sử dụng như sau:

```java
yield <value>;
```

### Chi Tiết
- **Ngữ cảnh sử dụng**: "yield" có thể được áp dụng trong các phương thức, đặc biệt là trong các phương thức được đánh dấu là `switch` expression.
- **Chạy luồng**: Khi từ khóa "yield" được gọi, luồng hiện tại sẽ tạm dừng và trả về giá trị cho phần gọi, cho phép các luồng khác có thể tiếp tục thực hiện.

## Ví Dụ
### Ví dụ 1: Sử Dụng yield trong Switch Expression
```java
int dayOfWeek = 3;
String dayType = switch (dayOfWeek) {
    case 1, 7 -> yield "Cuối tuần";
    case 2, 3, 4, 5, 6 -> yield "Ngày thường";
    default -> yield "Không hợp lệ";
};
System.out.println(dayType); // In ra: Ngày thường
```

### Ví dụ 2: Sử Dụng yield trong Record
```java
record Point(int x, int y) {
    public int distanceFromOrigin() {
        return yield (int) Math.sqrt(x * x + y * y);
    }
}
Point p = new Point(3, 4);
System.out.println(p.distanceFromOrigin()); // In ra: 5
```

## Giải Thích
### Các Cạm Bẫy Thường Gặp
- **Không sử dụng yield trong phương thức thông thường**: "yield" chỉ có hiệu lực trong một số ngữ cảnh nhất định như switch expression và không nên được sử dụng như một từ khóa độc lập trong các phương thức thông thường.
- **Nhầm lẫn với return**: Mặc dù "yield" có chức năng tương tự như "return", nhưng "yield" cho phép tạm dừng luồng và trả về trong các ngữ cảnh đặc biệt, không phải là một lựa chọn thay thế cho "return" trong mọi trường hợp.

## Tóm Tắt Một Câu
Từ khóa "yield" trong Java cho phép tạm dừng một luồng và trả về giá trị trong ngữ cảnh của các biểu thức lambda và switch expression, mang lại sự linh hoạt trong quản lý luồng.