<!--
Meta Description: # Java의 "protected" 접근 제어자에 대한 완벽 가이드 ## 개요 Java에서 "protected"는 클래스의 멤버에 대한 접근을 제어하는 접근 제어자입니다. 이는 상속 관계에 있는 클래스에서만 접근을 허용하며, 같은 패키지 내의 클래스에서도 사용할 수 있...
Meta Keywords: protected, 접근할, 있습니다, java, public
-->

# Java의 "protected" 접근 제어자에 대한 완벽 가이드

## 개요
Java에서 "protected"는 클래스의 멤버에 대한 접근을 제어하는 접근 제어자입니다. 이는 상속 관계에 있는 클래스에서만 접근을 허용하며, 같은 패키지 내의 클래스에서도 사용할 수 있습니다.

## 문서화
Java에서 "protected" 접근 제어자는 클래스의 필드, 메서드, 생성자에 적용될 수 있습니다. 이 접근 제어자를 사용하면 다음과 같은 목적을 달성할 수 있습니다:

- **상속**: "protected" 멤버는 서브 클래스에서 접근할 수 있습니다. 이는 코드 재사용성을 높이고, 객체 지향 프로그래밍의 상속 개념을 활용할 수 있게 합니다.
- **패키지 접근**: 동일 패키지 내의 모든 클래스는 "protected" 멤버에 접근할 수 있습니다. 이는 서로 관련이 있는 클래스 간의 상호작용을 용이하게 합니다.

"protected" 접근 제어자는 다음과 같은 형식으로 사용됩니다:

```java
protected 데이터형 변수명;
protected 반환형 메서드명() { ... }
```

## 예제
다음은 "protected" 접근 제어자를 사용하는 간단한 예제입니다:

```java
// BaseClass.java
package mypackage;

public class BaseClass {
    protected String protectedField = "Hello, protected!";

    protected void protectedMethod() {
        System.out.println("This is a protected method.");
    }
}

// SubClass.java
package mypackage;

public class SubClass extends BaseClass {
    public void display() {
        System.out.println(protectedField);
        protectedMethod();
    }
}

// Main.java
package mypackage;

public class Main {
    public static void main(String[] args) {
        SubClass obj = new SubClass();
        obj.display();
    }
}
```

위의 예제에서 `BaseClass`의 `protectedField`와 `protectedMethod`는 `SubClass`에서 접근할 수 있습니다.

## 설명
"protected" 접근 제어자를 사용할 때 주의해야 할 점은 다음과 같습니다:

- **다른 패키지에서의 접근**: "protected" 멤버는 상속 관계에 있는 클래스에서만 접근할 수 있으며, 다른 패키지에 있는 클래스에서는 직접 접근할 수 없습니다.
- **직접 인스턴스화**: 다른 패키지에 있는 클래스에서 `protected` 멤버를 직접 인스턴스화 하려고 할 경우, 접근할 수 없으므로 컴파일 오류가 발생합니다.
- **구조적 설계**: "protected" 멤버를 과도하게 사용하는 것은 클래스의 캡슐화를 해칠 수 있으므로 주의해야 합니다.

## 한 줄 요약
Java에서 "protected" 접근 제어자는 상속된 클래스와 동일 패키지 내의 클래스에서 접근할 수 있는 멤버를 정의합니다.