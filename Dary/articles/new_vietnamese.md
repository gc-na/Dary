<!--
Meta Description: # Từ Khóa "new" trong JAVA: Tạo Đối Tượng Mới ## Tóm Tắt Từ khóa `new` trong JAVA được sử dụng để khởi tạo một đối tượng mới từ một lớp đã được định n...
Meta Keywords: đối, tượng, new, tạo, được
-->

# Từ Khóa "new" trong JAVA: Tạo Đối Tượng Mới

## Tóm Tắt
Từ khóa `new` trong JAVA được sử dụng để khởi tạo một đối tượng mới từ một lớp đã được định nghĩa. Đây là một phần quan trọng trong lập trình hướng đối tượng, cho phép người lập trình tạo ra các instance (thể hiện) của lớp.

## Tài Liệu
### Mục Đích
Từ khóa `new` cho phép lập trình viên tạo ra các đối tượng bằng cách gọi constructor (hàm khởi tạo) của một lớp. Điều này là cần thiết để sử dụng các thuộc tính và phương thức của lớp đó.

### Cách Sử Dụng
Cú pháp cơ bản để sử dụng từ khóa `new` là:

```java
ClassName objectName = new ClassName();
```

Trong đó:
- `ClassName` là tên lớp mà bạn muốn khởi tạo.
- `objectName` là biến tham chiếu đến đối tượng đó.

### Chi Tiết
- Khi bạn sử dụng `new`, bộ nhớ sẽ được cấp phát cho đối tượng mới và constructor tương ứng sẽ được gọi.
- Các constructor có thể có tham số, và bạn có thể truyền các giá trị vào để khởi tạo đối tượng theo cách cụ thể.
- Nếu không có constructor được định nghĩa, JAVA sẽ tự động cung cấp một constructor mặc định không có tham số.

## Ví Dụ
### Ví dụ 1: Khởi Tạo Đối Tượng Cơ Bản
```java
public class Dog {
    String name;

    // Constructor
    Dog(String name) {
        this.name = name;
    }
}

public class Main {
    public static void main(String[] args) {
        Dog myDog = new Dog("Buddy");
        System.out.println("Tên chó là: " + myDog.name);
    }
}
```

### Ví dụ 2: Sử Dụng Constructor Mặc Định
```java
public class Cat {
    String name;

    // Constructor mặc định
    Cat() {
        this.name = "Mèo không tên";
    }
}

public class Main {
    public static void main(String[] args) {
        Cat myCat = new Cat();
        System.out.println("Tên mèo là: " + myCat.name);
    }
}
```

## Giải Thích
- **Lỗi phổ biến**: Một số lập trình viên có thể quên gọi từ khóa `new` khi cố gắng tạo một đối tượng, gây ra lỗi biên dịch. Ví dụ, nếu bạn chỉ viết `Dog myDog = Dog();`, điều này sẽ không hợp lệ.
- **Chú ý về bộ nhớ**: Mỗi lần bạn sử dụng `new`, một đối tượng mới sẽ được tạo và bộ nhớ sẽ được cấp phát. Nếu không sử dụng đối tượng đó, nó có thể dẫn đến rò rỉ bộ nhớ nếu không được thu dọn đúng cách.
- **Khả năng tái sử dụng**: Đối tượng được tạo ra bằng `new` có thể được sử dụng nhiều lần trong chương trình, nhưng mỗi lần bạn gọi `new`, một thể hiện mới sẽ được tạo ra.

## Tóm Tắt Một Dòng
Từ khóa `new` trong JAVA được sử dụng để khởi tạo các đối tượng mới từ lớp, là một phần thiết yếu của lập trình hướng đối tượng.