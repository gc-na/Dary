<!--
Meta Description: # JAVA에서의 static 키워드: 사용법과 이해 ## 개요 JAVA에서 `static` 키워드는 클래스의 속성이나 메서드를 정의할 때 사용되며, 인스턴스가 아닌 클래스 자체에 속하는 것을 의미합니다. 이 키워드는 메모리 관리와 코드 효율성을 높이는 데 중요한 역할...
Meta Keywords: static, 인스턴스, counter, 클래스의, count
-->

# JAVA에서의 static 키워드: 사용법과 이해

## 개요
JAVA에서 `static` 키워드는 클래스의 속성이나 메서드를 정의할 때 사용되며, 인스턴스가 아닌 클래스 자체에 속하는 것을 의미합니다. 이 키워드는 메모리 관리와 코드 효율성을 높이는 데 중요한 역할을 합니다.

## 문서화
`static` 키워드는 JAVA에서 클래스의 멤버(변수와 메서드)가 인스턴스가 아닌 클래스에 속하도록 하는 데 사용됩니다. 즉, `static`으로 선언된 멤버는 클래스의 모든 인스턴스가 공유하며, 클래스가 메모리에 로드될 때 단 한 번만 메모리에 할당됩니다.

### 목적
- 메모리 절약: 클래스의 모든 객체가 동일한 공간을 사용하므로 메모리 사용량을 줄일 수 있습니다.
- 유틸리티 메서드: 특정 기능을 제공하는 메서드를 클래스에 묶어 쉽게 접근할 수 있도록 합니다.
- 전역 상태 관리: `static` 변수를 사용하여 클래스 레벨에서 상태를 관리할 수 있습니다.

### 사용법
`static` 키워드는 다음과 같은 경우에 사용됩니다:
1. **변수**: 클래스의 모든 인스턴스가 공유하는 변수를 정의할 때 사용합니다.
   ```java
   class Example {
       static int staticVariable = 0;
   }
   ```

2. **메서드**: 인스턴스 없이 호출할 수 있는 메서드를 정의할 때 사용합니다.
   ```java
   class Example {
       static void staticMethod() {
           System.out.println("This is a static method");
       }
   }
   ```

3. **블록**: 클래스가 로드될 때 실행되는 초기화 블록을 정의할 때 사용됩니다.
   ```java
   class Example {
       static {
           System.out.println("Static block initialized");
       }
   }
   ```

## 예제
다음은 `static` 키워드의 기본 사용법을 보여주는 간단한 예제입니다.

```java
public class Counter {
    static int count = 0; // static 변수

    public Counter() {
        count++; // 생성자에서 count 증가
    }

    static void displayCount() { // static 메서드
        System.out.println("Current count: " + count);
    }

    public static void main(String[] args) {
        Counter c1 = new Counter();
        Counter c2 = new Counter();
        Counter.displayCount(); // 출력: Current count: 2
    }
}
```

## 설명
- **인스턴스와의 차이**: `static` 멤버는 클래스가 메모리에 로드될 때 할당되며, 모든 인스턴스에서 동일한 값을 공유합니다. 반면, 인스턴스 변수는 각각의 객체마다 개별적으로 존재합니다.
- **정적 메서드**: `static` 메서드는 클래스의 인스턴스 없이 호출할 수 있으며, 인스턴스 변수나 메서드에 접근할 수 없습니다. 이는 주의가 필요합니다.
- **정적 초기화 블록**: 클래스가 처음 로드될 때 실행되며, 정적 변수를 초기화하는 데 유용합니다.

### 일반적인 함정
- **정적 메서드에서 인스턴스 변수 접근**: 정적 메서드에서는 인스턴스 변수에 직접 접근할 수 없습니다. 이를 피하기 위해서는 인스턴스를 생성하거나 인스턴스 메서드를 호출해야 합니다.
- **스레드 안전성**: `static` 변수를 사용할 때는 여러 스레드에서 접근하는 경우 동기화 문제에 주의해야 합니다.

## 한 줄 요약
`static`은 JAVA에서 클래스에 속하는 변수와 메서드를 정의하는 데 사용되며, 메모리 관리와 코드 효율성을 향상시킵니다.