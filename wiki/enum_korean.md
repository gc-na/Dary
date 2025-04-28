<!--
Meta Description: # Java의 Enum: 열거형 타입에 대한 완벽 가이드 ## 개요 Java의 `enum`은 상수 집합을 정의하고, 각 상수를 객체처럼 다룰 수 있도록 해주는 특별한 데이터 타입입니다. 이를 통해 코드의 가독성과 유지보수성을 높일 수 있습니다. ## 문서화 `enum`...
Meta Keywords: enum, 있습니다, 열거형, java, public
-->

# Java의 Enum: 열거형 타입에 대한 완벽 가이드

## 개요
Java의 `enum`은 상수 집합을 정의하고, 각 상수를 객체처럼 다룰 수 있도록 해주는 특별한 데이터 타입입니다. 이를 통해 코드의 가독성과 유지보수성을 높일 수 있습니다.

## 문서화
`enum`은 Java 5에서 도입된 기능으로, 열거형 타입을 정의하는 데 사용됩니다. 열거형 타입은 관련된 상수 집합을 정의하고, 각 상수는 `enum` 타입의 인스턴스로 취급됩니다. `enum`은 가독성이 좋고, 타입 안전성을 제공하며, switch 문과 함께 사용하기에 적합합니다.

### 목적
- 코드의 가독성을 높이고, 상수 관리를 용이하게 합니다.
- 타입 안전성을 제공하여 잘못된 값 사용을 방지합니다.
- 관련 상수들을 그룹화하여 논리적인 구조를 제공합니다.

### 사용법
`enum`은 다음과 같이 정의합니다:

```java
public enum Color {
    RED, GREEN, BLUE;
}
```

각 상수는 `Color.RED`, `Color.GREEN`, `Color.BLUE`와 같이 사용됩니다. `enum`은 클래스처럼 메서드와 필드를 가질 수 있으며, 생성자를 정의할 수 있습니다.

### 세부 사항
- `enum`은 기본적으로 `java.lang.Enum` 클래스를 상속합니다.
- `enum`의 각 상수는 고유한 인스턴스입니다.
- `enum`의 메서드는 `switch` 문에서 사용할 수 있습니다.

## 예제
기본적인 `enum` 사용 예제는 다음과 같습니다:

```java
public enum Day {
    SUNDAY, MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY
}

public class Main {
    public static void main(String[] args) {
        Day today = Day.WEDNESDAY;

        switch (today) {
            case SUNDAY:
                System.out.println("일요일입니다.");
                break;
            case MONDAY:
                System.out.println("월요일입니다.");
                break;
            // 나머지 경우 생략
            default:
                System.out.println("주중입니다.");
        }
    }
}
```

## 설명
- **공통적인 실수**: `enum`을 사용할 때 상수를 잘못 지정하는 오류가 발생할 수 있습니다. 예를 들어, `Day.MONDAY`가 아닌 문자열로 직접 비교하는 것은 잘못된 코드입니다.
- **열거형의 확장**: `enum`은 인터페이스를 구현할 수 있으며, 메서드를 정의할 수 있습니다. 각 상수마다 다르게 동작하도록 메서드를 오버라이드할 수 있습니다.
- **연관된 데이터**: 열거형 상수에 추가적인 데이터를 연결할 수 있습니다. 예를 들어, 색상과 그에 대한 RGB 값을 연결할 수 있습니다.

## 한 줄 요약
Java의 `enum`은 관련 상수 집합을 정의하여 코드의 가독성을 높이고 타입 안전성을 제공하는 열거형 타입입니다.