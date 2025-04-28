<!--
Meta Description: # Từ Khóa "protected" trong JAVA: Đặc Điểm và Cách Sử Dụng ## Tóm tắt Trong ngôn ngữ lập trình JAVA, từ khóa `protected` được sử dụng để xác định cấp ...
Meta Keywords: lớp, protected, trong, các, một
-->

# Từ Khóa "protected" trong JAVA: Đặc Điểm và Cách Sử Dụng

## Tóm tắt
Trong ngôn ngữ lập trình JAVA, từ khóa `protected` được sử dụng để xác định cấp độ truy cập cho các thành viên trong lớp, cho phép chúng có thể được truy cập từ các lớp con và các lớp trong cùng gói.

## Tài liệu
Từ khóa `protected` là một trong bốn cấp độ truy cập trong JAVA, bao gồm `public`, `protected`, `default` (không có từ khóa) và `private`. Khi một thành viên của lớp (biến hoặc phương thức) được khai báo là `protected`, nó có thể được truy cập bởi:

1. Các lớp con (subclasses) của lớp đó, ngay cả khi chúng nằm ở các gói khác.
2. Các lớp trong cùng một gói.

### Mục đích
Cấp độ truy cập `protected` giúp bảo vệ các dữ liệu nhạy cảm của lớp, đồng thời cho phép các lớp con truy cập và sử dụng những dữ liệu đó một cách an toàn. Điều này rất hữu ích trong lập trình hướng đối tượng, nơi mà việc kế thừa (inheritance) thường xuyên được sử dụng.

### Cách sử dụng
Để khai báo một biến hoặc phương thức là `protected`, bạn chỉ cần thêm từ khóa `protected` trước kiểu dữ liệu hoặc trước tên phương thức, như sau:

```java
protected int myProtectedVariable;
protected void myProtectedMethod() {
    // Thực hiện một số công việc
}
```

## Ví dụ
Dưới đây là một ví dụ đơn giản minh họa cách sử dụng từ khóa `protected` trong JAVA:

```java
// Lớp Cha
class Animal {
    protected void sound() {
        System.out.println("Âm thanh của động vật");
    }
}

// Lớp Con
class Dog extends Animal {
    void bark() {
        sound(); // Gọi phương thức protected từ lớp cha
        System.out.println("Gâu gâu");
    }
}

// Lớp chính
public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.bark(); // Kết quả: Âm thanh của động vật
                     // Gâu gâu
    }
}
```

Trong ví dụ này, phương thức `sound()` được khai báo là `protected`, cho phép lớp `Dog` kế thừa và gọi nó.

## Giải thích
Một số điểm cần lưu ý khi sử dụng từ khóa `protected`:

- **Không thể truy cập từ bên ngoài:** Nếu bạn cố gắng truy cập một thành viên `protected` từ một lớp không phải là lớp con hoặc không nằm trong cùng gói, bạn sẽ nhận được lỗi biên dịch.
  
- **Kế thừa:** Khi một lớp con kế thừa từ lớp cha, nó có quyền truy cập vào các thành viên `protected`, nhưng điều này không áp dụng cho các lớp khác không liên quan.

- **Tính bảo mật:** Mặc dù `protected` cho phép truy cập từ lớp con, bạn vẫn nên cẩn thận với việc thiết kế API, tránh lạm dụng tính năng này để bảo vệ sự riêng tư của dữ liệu.

## Tóm tắt một dòng
Từ khóa `protected` trong JAVA cho phép các thành viên của lớp được truy cập từ các lớp con và các lớp trong cùng gói, giúp hỗ trợ cho việc kế thừa và bảo vệ dữ liệu.