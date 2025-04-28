<!--
Meta Description: # Giao Diện (Interface) trong Java: Tìm Hiểu và Ví Dụ Cụ Thể ## Tóm Tắt Giao diện (interface) trong Java là một cách để định nghĩa một tập hợp các phư...
Meta Keywords: diện, giao, một, lớp, java
-->

# Giao Diện (Interface) trong Java: Tìm Hiểu và Ví Dụ Cụ Thể

## Tóm Tắt
Giao diện (interface) trong Java là một cách để định nghĩa một tập hợp các phương thức mà các lớp phải triển khai, giúp tăng cường tính linh hoạt và khả năng mở rộng của mã nguồn.

## Tài Liệu
Trong Java, giao diện là một loại kiểu dữ liệu đặc biệt, cho phép bạn xác định các phương thức mà không cần cung cấp cài đặt cho chúng. Giao diện có thể được xem như một hợp đồng mà các lớp thực hiện phải tuân theo. Một lớp có thể thực hiện nhiều giao diện, điều này giúp Java hỗ trợ tính đa hình và khả năng tái sử dụng mã.

### Mục Đích
- **Định nghĩa hành vi**: Giao diện cho phép xác định các phương thức mà lớp thực hiện cần có.
- **Hỗ trợ tính đa hình**: Các lớp khác nhau có thể có cài đặt khác nhau cho các phương thức trong cùng một giao diện.
- **Tăng tính linh hoạt**: Cho phép thay đổi cài đặt mà không làm thay đổi mã nguồn của lớp sử dụng giao diện.

### Cách Sử Dụng
Để tạo một giao diện trong Java, bạn sử dụng từ khóa `interface`. Các phương thức trong giao diện tự động được coi là `public` và `abstract`, vì vậy không cần phải khai báo chúng. Một lớp có thể thực hiện giao diện bằng cách sử dụng từ khóa `implements`.

#### Cú Pháp:
```java
interface TenGiaoDien {
    void phuongThuc1();
    int phuongThuc2(String thamSo);
}
```

```java
class LopThucHien implements TenGiaoDien {
    @Override
    public void phuongThuc1() {
        // cài đặt phương thức
    }

    @Override
    public int phuongThuc2(String thamSo) {
        // cài đặt phương thức
        return 0;
    }
}
```

## Ví Dụ
### Ví dụ 1: Giao diện đơn giản
```java
interface Hinh {
    double dienTich();
}

class HinhVuong implements Hinh {
    private double canh;

    public HinhVuong(double canh) {
        this.canh = canh;
    }

    @Override
    public double dienTich() {
        return canh * canh;
    }
}

public class Main {
    public static void main(String[] args) {
        Hinh hinhVuong = new HinhVuong(5);
        System.out.println("Diện tích hình vuông: " + hinhVuong.dienTich());
    }
}
```

### Ví dụ 2: Giao diện với nhiều lớp thực hiện
```java
interface DongVat {
    void keu();
}

class Cho implements DongVat {
    @Override
    public void keu() {
        System.out.println("Gâu gâu!");
    }
}

class Meo implements DongVat {
    @Override
    public void keu() {
        System.out.println("Meo meo!");
    }
}

public class Main {
    public static void main(String[] args) {
        DongVat cho = new Cho();
        DongVat meo = new Meo();
        cho.keu();
        meo.keu();
    }
}
```

## Giải Thích
Khi làm việc với giao diện trong Java, có một số điều cần lưu ý:
- **Nhiều lớp thực hiện**: Một giao diện có thể được nhiều lớp thực hiện, nhưng một lớp chỉ có thể kế thừa một lớp cha.
- **Không có trạng thái**: Giao diện không thể có biến trạng thái (instance variables), chỉ có thể chứa các phương thức.
- **Java 8 trở đi**: Giao diện có thể chứa các phương thức mặc định (default method) và phương thức tĩnh (static method).

## Tóm Tắt Một Câu
Giao diện trong Java cho phép định nghĩa các phương thức mà các lớp thực hiện phải tuân theo, giúp tăng cường tính linh hoạt và khả năng mở rộng của mã nguồn.