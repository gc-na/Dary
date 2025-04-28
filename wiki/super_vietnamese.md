<!--
Meta Description: # Từ Khóa "super" trong JAVA: Tính Năng và Cách Sử Dụng ## Tóm Tắt Từ khóa `super` trong JAVA được sử dụng để tham chiếu đến lớp cha (superclass) của ...
Meta Keywords: lớp, của, super, trong, cha
-->

# Từ Khóa "super" trong JAVA: Tính Năng và Cách Sử Dụng

## Tóm Tắt
Từ khóa `super` trong JAVA được sử dụng để tham chiếu đến lớp cha (superclass) của một lớp cụ thể (subclass). Nó cho phép lập trình viên truy cập các thuộc tính và phương thức của lớp cha, hỗ trợ trong việc kế thừa và mở rộng các tính năng của lớp cha.

## Tài Liệu
### Mục Đích
`super` được sử dụng trong hai trường hợp chính:
1. **Gọi phương thức của lớp cha**: Khi bạn muốn sử dụng một phương thức được định nghĩa trong lớp cha mà đã bị ghi đè (overridden) trong lớp con.
2. **Truy cập thuộc tính của lớp cha**: Khi bạn cần truy cập các biến thành viên (instance variables) của lớp cha mà có cùng tên với biến trong lớp con.

### Cách Sử Dụng
- **Cú pháp**: `super.methodName();` để gọi phương thức và `super.variableName` để truy cập thuộc tính.
- **Gọi constructor của lớp cha**: `super(parameters);` có thể được sử dụng trong constructor của lớp con để gọi constructor của lớp cha.

### Chi Tiết
- `super` phải được gọi trước tiên trong constructor của lớp con nếu bạn sử dụng nó.
- `super` không thể được sử dụng trong các phương thức tĩnh (static methods).
- Trong trường hợp phương thức bị ghi đè, bạn có thể sử dụng `super` để gọi phiên bản của phương thức từ lớp cha.

## Ví Dụ
```java
class Animal {
    void sound() {
        System.out.println("Animal makes sound");
    }
}

class Dog extends Animal {
    void sound() {
        super.sound(); // Gọi phương thức sound() của lớp Animal
        System.out.println("Dog barks");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.sound();
    }
}
```

Kết quả sẽ là:
```
Animal makes sound
Dog barks
```

### Truy Cập Thuộc Tính
```java
class Parent {
    String name = "Parent";
}

class Child extends Parent {
    String name = "Child";

    void displayNames() {
        System.out.println("Child name: " + name);
        System.out.println("Parent name: " + super.name); // Truy cập thuộc tính name của lớp Parent
    }
}

public class Main {
    public static void main(String[] args) {
        Child child = new Child();
        child.displayNames();
    }
}
```

Kết quả sẽ là:
```
Child name: Child
Parent name: Parent
```

## Giải Thích
- **Lỗi phổ biến**: Một số lập trình viên có thể nhầm lẫn giữa việc sử dụng `super` và `this`. `this` tham chiếu đến đối tượng hiện tại, trong khi `super` tham chiếu đến lớp cha.
- **Ghi đè phương thức**: Khi bạn ghi đè phương thức, hãy nhớ rằng bạn có thể vẫn cần gọi phương thức của lớp cha để giữ lại một số hành vi cũ.
- **Constructor**: Nếu bạn không gọi `super()` trong constructor, JAVA sẽ tự động gọi constructor không tham số của lớp cha.

## Tóm Tắt Một Dòng
Từ khóa `super` trong JAVA cho phép truy cập các phương thức và thuộc tính của lớp cha, hỗ trợ lập trình viên trong việc sử dụng và mở rộng tính năng của lớp cha.