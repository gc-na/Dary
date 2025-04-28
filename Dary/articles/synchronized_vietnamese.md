<!--
Meta Description: # Synchronized trong Java: Cách Đồng Bộ Hóa Đa Luồng ## Tóm tắt "Synchronized" là một từ khóa trong Java được sử dụng để kiểm soát quyền truy cập đồng...
Meta Keywords: synchronized, một, đồng, dụng, hóa
-->

# Synchronized trong Java: Cách Đồng Bộ Hóa Đa Luồng

## Tóm tắt
"Synchronized" là một từ khóa trong Java được sử dụng để kiểm soát quyền truy cập đồng thời vào các phương thức hoặc khối mã, giúp tránh tình trạng rối loạn dữ liệu khi nhiều luồng cùng truy cập vào tài nguyên chia sẻ.

## Tài liệu
### Mục đích
Từ khóa "synchronized" trong Java đảm bảo rằng một phương thức hoặc khối mã chỉ có thể được thực thi bởi một luồng tại một thời điểm. Điều này rất quan trọng trong các ứng dụng đa luồng, nơi nhiều luồng có thể cố gắng truy cập và sửa đổi cùng một tài nguyên đồng thời.

### Cách sử dụng
Có hai cách chính để sử dụng từ khóa "synchronized":

1. **Synchronized Method**: Bạn có thể sử dụng "synchronized" trước khai báo phương thức để đồng bộ hóa toàn bộ phương thức.
   ```java
   public synchronized void methodName() {
       // code cần đồng bộ hóa
   }
   ```

2. **Synchronized Block**: Bạn có thể sử dụng "synchronized" để đồng bộ hóa một khối mã, cho phép chỉ một phần của phương thức được đồng bộ hóa.
   ```java
   public void methodName() {
       synchronized (this) {
           // code cần đồng bộ hóa
       }
   }
   ```

### Chi tiết
- **Synchronized Instance Methods**: Khi một phương thức được đánh dấu là synchronized, nó sẽ khóa đối tượng hiện tại (this). Điều này có nghĩa là chỉ một luồng có thể truy cập vào phương thức đó tại một thời điểm.
  
- **Synchronized Static Methods**: Đối với các phương thức tĩnh, "synchronized" sẽ khóa class, vì vậy chỉ một luồng có thể truy cập vào phương thức tĩnh tại một thời điểm.
  
- **Synchronized Blocks**: Thay vì đồng bộ hóa toàn bộ phương thức, bạn có thể chỉ định một đối tượng cụ thể để đồng bộ hóa, giúp tăng cường hiệu suất bằng cách giảm thời gian khóa.

## Ví dụ
### Ví dụ 1: Synchronized Method
```java
public class Counter {
    private int count = 0;

    public synchronized void increment() {
        count++;
    }

    public int getCount() {
        return count;
    }
}
```

### Ví dụ 2: Synchronized Block
```java
public class Counter {
    private int count = 0;

    public void increment() {
        synchronized (this) {
            count++;
        }
    }

    public int getCount() {
        return count;
    }
}
```

## Giải thích
Một số điều cần lưu ý khi sử dụng từ khóa "synchronized":
- **Hiệu suất**: Sử dụng "synchronized" có thể làm giảm hiệu suất do thời gian khóa. Nên chỉ sử dụng khi cần thiết.
- **Deadlock**: Cảnh giác với tình trạng deadlock, khi hai hoặc nhiều luồng chờ nhau để giải phóng khóa mà không bao giờ có thể tiến lên.
- **Không đồng bộ hóa trên các biến tĩnh**: Nếu cần đồng bộ hóa trên biến tĩnh, bạn cần sử dụng khóa cho class thay vì đối tượng.

## Tóm tắt một câu
"Synchronized" trong Java là một công cụ cần thiết để đảm bảo an toàn đồng thời trong các ứng dụng đa luồng bằng cách kiểm soát quyền truy cập vào tài nguyên chia sẻ.