<!--
Meta Description: # JAVA의 "default" 키워드: 이해와 활용 ## 개요 Java에서 "default" 키워드는 주로 인터페이스에서 사용되며, 인터페이스에 기본 구현을 제공하는 기능을 나타냅니다. 이는 Java 8에서 도입되어 인터페이스 설계의 유연성을 높이고, 기존 인터페이스...
Meta Keywords: 메소드를, public, default, void, 인터페이스에
-->

# JAVA의 "default" 키워드: 이해와 활용

## 개요
Java에서 "default" 키워드는 주로 인터페이스에서 사용되며, 인터페이스에 기본 구현을 제공하는 기능을 나타냅니다. 이는 Java 8에서 도입되어 인터페이스 설계의 유연성을 높이고, 기존 인터페이스에 새로운 메소드를 추가할 때의 호환성 문제를 해결하는 데 도움을 줍니다.

## 문서화

### 목적
"Default" 키워드는 인터페이스 내에서 메소드에 기본 구현을 정의할 수 있게 해줍니다. 이는 인터페이스를 구현하는 클래스가 메소드를 오버라이드하지 않더라도, 기본적인 기능을 사용할 수 있도록 합니다.

### 사용법
인터페이스에 `default` 키워드를 사용하여 기본 메소드를 선언합니다. 이를 통해 기존 인터페이스에 새로운 메소드를 추가해도, 이를 구현하는 클래스에 영향을 미치지 않게 됩니다.

```java
public interface MyInterface {
    default void defaultMethod() {
        System.out.println("기본 메소드 구현");
    }
}
```

### 세부사항
- **변경 호환성**: 기존 인터페이스에 새로운 메소드를 추가할 때, 이를 구현하는 모든 클래스가 변경하지 않아도 되므로 코드의 유연성을 제공합니다.
- **다중 상속**: 기본 메소드를 사용할 때, 만약 여러 인터페이스에서 같은 이름의 기본 메소드를 가진 경우, 이를 구현하는 클래스는 어떤 메소드를 사용할지 명시해야 합니다.
- **추상 메소드와의 조화**: 인터페이스는 여전히 추상 메소드를 가질 수 있으며, 이를 구현하는 클래스는 필요에 따라 기본 메소드를 오버라이드할 수 있습니다.

## 예제

### 기본 사용 예
```java
public interface Vehicle {
    default void start() {
        System.out.println("차량이 시작되었습니다.");
    }
}

public class Car implements Vehicle {
    public void start() {
        System.out.println("자동차가 시작되었습니다.");
    }
}

public class Main {
    public static void main(String[] args) {
        Car car = new Car();
        car.start(); // 출력: 자동차가 시작되었습니다.
    }
}
```

### 기본 메소드 사용 예
```java
public interface Printer {
    default void print() {
        System.out.println("기본 프린터입니다.");
    }
}

public class MyPrinter implements Printer {
    // 기본 메소드 오버라이드
    public void print() {
        System.out.println("사용자 정의 프린터입니다.");
    }
}

public class Main {
    public static void main(String[] args) {
        MyPrinter printer = new MyPrinter();
        printer.print(); // 출력: 사용자 정의 프린터입니다.
    }
}
```

## 설명
- **공통 문제점**: 여러 인터페이스가 같은 이름의 기본 메소드를 가질 때, 이를 구현하는 클래스에서 어떤 메소드를 사용할지 명시적으로 해결해야 합니다. 이 경우, `super` 키워드를 사용하여 특정 인터페이스의 기본 메소드를 호출할 수 있습니다.
  
- **제한 사항**: 기본 메소드는 `static`이나 `private`으로 선언할 수 없습니다. 기본 메소드는 인터페이스 내에서만 사용 가능하며, 클래스에서는 사용할 수 없습니다.

## 한 줄 요약
Java의 "default" 키워드는 인터페이스에 기본 구현을 제공하여 코드의 호환성과 유연성을 높이는 기능입니다.