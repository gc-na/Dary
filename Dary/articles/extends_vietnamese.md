<!--
Meta Description: # Từ Khóa "extends" trong Java: Cách Kế Thừa Lớp Trong Lập Trình Hướng Đối Tượng ## Tóm tắt Từ khóa "extends" trong Java được sử dụng để chỉ định rằng...
Meta Keywords: lớp, một, extends, thừa, phương
-->

# Từ Khóa "extends" trong Java: Cách Kế Thừa Lớp Trong Lập Trình Hướng Đối Tượng

## Tóm tắt
Từ khóa "extends" trong Java được sử dụng để chỉ định rằng một lớp mới kế thừa từ một lớp hiện có, cho phép tái sử dụng mã và mở rộng chức năng của lớp cha.

## Tài liệu
Từ khóa "extends" là một phần quan trọng trong lập trình hướng đối tượng với Java. Nó cho phép một lớp (được gọi là lớp con) kế thừa thuộc tính và phương thức từ một lớp khác (được gọi là lớp cha). Sử dụng "extends" giúp giảm thiểu việc lặp mã và tối ưu hóa quá trình phát triển phần mềm.

### Mục đích
Mục đích chính của từ khóa "extends" là để tạo ra một mối quan hệ giữa các lớp, cho phép lớp con kế thừa các thành phần của lớp cha. Điều này không chỉ giúp tăng cường khả năng tái sử dụng mã mà còn hỗ trợ cho nguyên tắc mở rộng và đóng gói trong lập trình hướng đối tượng.

### Cách sử dụng
Cú pháp để sử dụng từ khóa "extends" trong Java như sau:

```java
class LớpCha {
    // Các thuộc tính và phương thức của lớp cha
}

class LớpCon extends LớpCha {
    // Các thuộc tính và phương thức của lớp con
}
```

Trong đó, `LớpCon` sẽ kế thừa tất cả các thuộc tính và phương thức của `LớpCha`, và có thể bổ sung thêm các thuộc tính hoặc phương thức riêng của nó.

## Ví dụ
Dưới đây là một số ví dụ về cách sử dụng từ khóa "extends" trong Java:

### Ví dụ 1: Kế thừa đơn giản

```java
class ĐộngVật {
    void ăn() {
        System.out.println("Động vật đang ăn");
    }
}

class Chó extends ĐộngVật {
    void sủa() {
        System.out.println("Chó đang sủa");
    }
}

public class Main {
    public static void main(String[] args) {
        Chó chó = new Chó();
        chó.ăn(); // Kế thừa từ ĐộngVật
        chó.sủa(); // Phương thức riêng của Chó
    }
}
```

### Ví dụ 2: Kế thừa với phương thức ghi đè

```java
class Xe {
    void diChuyen() {
        System.out.println("Xe đang di chuyển");
    }
}

class XeDap extends Xe {
    void diChuyen() {
        System.out.println("Xe đạp đang đạp");
    }
}

public class Main {
    public static void main(String[] args) {
        XeDap xeDap = new XeDap();
        xeDap.diChuyen(); // Ghi đè phương thức diChuyen
    }
}
```

## Giải thích
Khi sử dụng từ khóa "extends", có một số điểm cần lưu ý:

- **Chỉ có thể kế thừa một lớp**: Java không hỗ trợ kế thừa nhiều lớp, nghĩa là một lớp chỉ có thể kế thừa từ một lớp cha duy nhất. Điều này giúp tránh các vấn đề phức tạp như "Diamond Problem".
  
- **Phương thức ghi đè**: Khi lớp con ghi đè một phương thức của lớp cha, bạn có thể sử dụng từ khóa `super` để gọi phương thức của lớp cha nếu cần thiết.

- **Truy cập thuộc tính**: Lớp con có thể truy cập các thuộc tính công khai và bảo vệ của lớp cha, nhưng không thể truy cập thuộc tính riêng.

## Tóm tắt một dòng
Từ khóa "extends" trong Java cho phép một lớp kế thừa thuộc tính và phương thức từ lớp cha, tăng cường khả năng tái sử dụng mã trong lập trình hướng đối tượng.