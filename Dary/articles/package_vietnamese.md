<!--
Meta Description: # Tìm Hiểu Về Package Trong Java: Cấu Trúc, Cách Sử Dụng và Ví Dụ ## Tóm Tắt Package trong Java là một cơ chế tổ chức mã nguồn, giúp nhóm các lớp (cla...
Meta Keywords: package, java, dụng, tên, trong
-->

# Tìm Hiểu Về Package Trong Java: Cấu Trúc, Cách Sử Dụng và Ví Dụ

## Tóm Tắt
Package trong Java là một cơ chế tổ chức mã nguồn, giúp nhóm các lớp (class) và giao diện (interface) liên quan lại với nhau, từ đó tăng cường khả năng quản lý và tái sử dụng mã.

## Tài Liệu
### Mục Đích
Package là một phần quan trọng trong lập trình Java, giúp người lập trình tổ chức mã nguồn một cách hợp lý. Bằng cách sử dụng package, bạn có thể tránh xung đột tên giữa các lớp và dễ dàng quản lý các thư viện bên ngoài.

### Cách Sử Dụng
Để khai báo một package trong Java, bạn sử dụng từ khóa `package`, theo sau là tên package. Cách thức khai báo này thường được đặt ở đầu tệp nguồn Java. Ví dụ:

```java
package com.example.myapp;
```

### Chi Tiết
- **Cấu Trúc Tên Package**: Tên package thường bao gồm tên miền đảo ngược (reverse domain name) và tên dự án, ví dụ: `com.google.android`.
- **Nhập Khẩu Package**: Để sử dụng các lớp từ package khác, bạn có thể sử dụng từ khóa `import`. Ví dụ:
  ```java
  import java.util.ArrayList;
  ```
- **Package Mặc Định**: Nếu bạn không khai báo package, lớp sẽ thuộc về package mặc định.
- **Quản Lý Thư Viện**: Thư viện bên ngoài thường được tổ chức trong các package riêng biệt, giúp dễ dàng quản lý và sử dụng.

## Ví Dụ
### Ví Dụ 1: Khai Báo Package
```java
package com.example.utility;

public class MathUtil {
    public static int add(int a, int b) {
        return a + b;
    }
}
```

### Ví Dụ 2: Sử Dụng Package
```java
package com.example.app;

import com.example.utility.MathUtil;

public class Main {
    public static void main(String[] args) {
        int result = MathUtil.add(5, 10);
        System.out.println("Kết quả: " + result);
    }
}
```

## Giải Thích
### Những Cái Bẫy Thông Thường
1. **Xung Đột Tên**: Nếu bạn có hai lớp cùng tên trong các package khác nhau, bạn cần chỉ định đầy đủ tên package khi sử dụng.
2. **Package Không Hợp Lệ**: Tên package không được chứa ký tự đặc biệt và phải tuân thủ quy tắc đặt tên của Java.
3. **Không Khai Báo Package**: Nếu bạn không khai báo package, lớp sẽ thuộc về package mặc định, có thể gây khó khăn trong việc quản lý mã nguồn.

## Tóm Tắt Một Câu
Package trong Java là cơ chế tổ chức mã nguồn giúp quản lý và tái sử dụng mã hiệu quả.