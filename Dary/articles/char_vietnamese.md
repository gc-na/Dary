<!--
Meta Description: # Tìm Hiểu Về Kiểu Dữ Liệu "char" Trong Java ## Tóm Tắt Trong ngôn ngữ lập trình Java, `char` là một kiểu dữ liệu nguyên thủy dùng để lưu trữ một ký t...
Meta Keywords: char, kiểu, trong, java, dụng
-->

# Tìm Hiểu Về Kiểu Dữ Liệu "char" Trong Java

## Tóm Tắt
Trong ngôn ngữ lập trình Java, `char` là một kiểu dữ liệu nguyên thủy dùng để lưu trữ một ký tự đơn. Nó chiếm 2 byte bộ nhớ và có thể đại diện cho các ký tự Unicode, cho phép lập trình viên thao tác với các ký tự một cách hiệu quả và dễ dàng.

## Tài Liệu
### Mục Đích
Kiểu dữ liệu `char` trong Java được thiết kế để lưu trữ các ký tự đơn, như chữ cái, chữ số, và các ký tự đặc biệt. Kiểu `char` có thể được sử dụng trong nhiều tình huống, từ việc xử lý văn bản đến việc xây dựng các giao diện người dùng.

### Cách Sử Dụng
Kiểu `char` được khai báo bằng cách sử dụng từ khóa `char`, theo sau là tên biến và có thể khởi tạo giá trị ngay lập tức. Một ký tự có thể được chỉ định bằng cách đặt nó trong dấu nháy đơn. Ví dụ:

```java
char letter = 'A';
char digit = '5';
char specialChar = '#';
```

### Chi Tiết
- `char` là một kiểu dữ liệu nguyên thủy trong Java.
- Ký tự được lưu trữ dưới dạng mã Unicode, cho phép sử dụng nhiều ngôn ngữ và ký tự khác nhau.
- Giá trị của `char` có thể được lấy bằng cách sử dụng toán tử chuyển đổi kiểu hoặc các phương thức trong lớp `Character`.

## Ví Dụ
Dưới đây là một số ví dụ cơ bản về cách sử dụng kiểu dữ liệu `char` trong Java:

### Ví dụ 1: Khai Báo và Khởi Tạo
```java
char letter = 'J';
System.out.println("Ký tự: " + letter);
```

### Ví dụ 2: Sử Dụng Trong Câu Lệnh Điều Kiện
```java
char grade = 'A';
if (grade == 'A') {
    System.out.println("Bạn đã đạt điểm cao!");
}
```

### Ví dụ 3: Tính Toán với Ký Tự
```java
char a = 'a';
char b = 'b';
int sum = a + b; // Kết quả là tổng mã Unicode của 2 ký tự
System.out.println("Tổng mã Unicode: " + sum);
```

## Giải Thích
Một số điểm cần lưu ý khi sử dụng kiểu `char`:
- Ký tự `char` không thể là chuỗi (String). Nếu bạn muốn lưu trữ nhiều ký tự, hãy sử dụng kiểu `String`.
- Kiểu `char` có thể biểu diễn các ký tự không phải ASCII, do đó cần cẩn thận khi làm việc với các hệ thống không hỗ trợ Unicode.
- Khi so sánh các ký tự, Java sử dụng giá trị Unicode của chúng, vì vậy `'A'` khác `'a'`.

## Tóm Tắt Một Dòng
Kiểu dữ liệu `char` trong Java là một kiểu nguyên thủy dùng để lưu trữ ký tự đơn, hoạt động với mã Unicode và dễ dàng sử dụng trong các tình huống lập trình khác nhau.