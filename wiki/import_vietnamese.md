<!--
Meta Description: # Lệnh "import" trong Java: Hướng Dẫn Chi Tiết ## Tóm tắt Lệnh `import` trong Java cho phép lập trình viên sử dụng các lớp và gói (packages) từ các th...
Meta Keywords: lớp, import, java, gói, trong
-->

# Lệnh "import" trong Java: Hướng Dẫn Chi Tiết

## Tóm tắt
Lệnh `import` trong Java cho phép lập trình viên sử dụng các lớp và gói (packages) từ các thư viện bên ngoài mà không cần phải chỉ định đường dẫn đầy đủ mỗi khi sử dụng.

## Tài liệu
### Mục đích
Lệnh `import` được sử dụng để đưa vào các lớp, gói và thư viện bên ngoài vào chương trình Java, giúp lập trình viên dễ dàng sử dụng các chức năng đã được định nghĩa trước mà không cần phải khai báo lại.

### Cách sử dụng
Cú pháp cơ bản của lệnh `import` như sau:
```java
import package_name.ClassName;
```
Hoặc để nhập tất cả các lớp trong một gói:
```java
import package_name.*;
```
Trong đó:
- `package_name` là tên gói mà lớp hoặc thư viện thuộc về.
- `ClassName` là tên lớp mà bạn muốn nhập.

### Chi tiết
- Lệnh `import` phải được đặt ở đầu file Java, trước khi định nghĩa lớp.
- Có thể sử dụng nhiều lệnh `import` trong một file.
- Java hỗ trợ nhập nhiều lớp từ cùng một gói trong một lệnh `import` bằng cách sử dụng ký tự `*`.

## Ví dụ
### Ví dụ 1: Nhập một lớp cụ thể
```java
import java.util.ArrayList;

public class Example {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();
        list.add("Hello, World!");
        System.out.println(list.get(0));
    }
}
```

### Ví dụ 2: Nhập tất cả các lớp trong một gói
```java
import java.util.*;

public class Example {
    public static void main(String[] args) {
        HashMap<String, Integer> map = new HashMap<>();
        map.put("One", 1);
        System.out.println(map.get("One"));
    }
}
```

## Giải thích
- **Nhập không chính xác**: Nếu bạn không nhập đúng tên gói hoặc lớp, trình biên dịch sẽ thông báo lỗi. Hãy chắc chắn rằng tên gói và lớp chính xác.
- **Tối ưu hóa nhập**: Chỉ nên nhập các lớp cần thiết để giảm thiểu kích thước của file biên dịch và tăng tốc độ thực thi.
- **Tổ chức gói**: Việc tổ chức các lớp trong gói một cách hợp lý sẽ giúp dễ dàng hơn trong việc sử dụng lệnh `import`.

## Tóm tắt một câu
Lệnh `import` trong Java cho phép lập trình viên dễ dàng sử dụng các lớp và gói bên ngoài mà không cần chỉ định đường dẫn đầy đủ.