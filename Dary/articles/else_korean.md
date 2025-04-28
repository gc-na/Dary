<!--
Meta Description: # Java의 else 문: 조건문 처리의 필수 요소 ## 개요 Java에서 `else` 문은 조건문인 `if`와 함께 사용되어 특정 조건이 거짓일 때 실행될 코드를 정의하는 기능입니다. 이를 통해 프로그램의 흐름을 제어하고, 다양한 상황에 대한 대응을 가능하게 합니다...
Meta Keywords: else, 조건이, false일, 실행되는, system
-->

# Java의 else 문: 조건문 처리의 필수 요소

## 개요
Java에서 `else` 문은 조건문인 `if`와 함께 사용되어 특정 조건이 거짓일 때 실행될 코드를 정의하는 기능입니다. 이를 통해 프로그램의 흐름을 제어하고, 다양한 상황에 대한 대응을 가능하게 합니다.

## 문서화
### 목적
`else` 문은 `if` 조건이 false일 경우 실행할 코드 블록을 정의하여, 조건에 따라 프로그램의 흐름을 변화시킬 수 있도록 돕습니다.

### 사용법
`else` 문은 `if` 문과 함께 사용되며, 다음과 같은 형식을 가집니다:

```java
if (조건) {
    // 조건이 true일 때 실행되는 코드
} else {
    // 조건이 false일 때 실행되는 코드
}
```

추가적으로 `else if` 문을 사용하여 여러 조건을 검사할 수 있습니다:

```java
if (조건1) {
    // 조건1이 true일 때 실행되는 코드
} else if (조건2) {
    // 조건2가 true일 때 실행되는 코드
} else {
    // 모든 조건이 false일 때 실행되는 코드
}
```

## 예제
### 기본 사용 예제
```java
public class Main {
    public static void main(String[] args) {
        int number = 10;

        if (number > 0) {
            System.out.println("양수입니다.");
        } else {
            System.out.println("양수가 아닙니다.");
        }
    }
}
```

### 여러 조건 검사
```java
public class Main {
    public static void main(String[] args) {
        int score = 85;

        if (score >= 90) {
            System.out.println("A");
        } else if (score >= 80) {
            System.out.println("B");
        } else {
            System.out.println("C");
        }
    }
}
```

## 설명
`else` 문 사용 시 주의할 점은 조건문 블록의 중괄호 `{}` 사용입니다. 한 줄의 코드만 포함될 경우 중괄호를 생략할 수 있지만, 가독성과 유지보수를 위해 명시적으로 사용하는 것이 좋습니다. 또한, `else` 문은 항상 `if` 문 뒤에 작성해야 하며, `else` 문이 없을 경우 조건이 false일 때 수행할 작업이 없음을 의미합니다.

### 일반적인 함정
1. **중괄호 생략**: 여러 줄의 코드를 작성할 때 중괄호를 생략하면 의도치 않은 결과를 초래할 수 있습니다.
2. **논리 연산자**: 여러 조건을 확인할 때, 논리 연산자(`&&`, `||`)를 사용하는 것을 잊지 마세요.
3. **코드 블록의 순서**: 조건의 순서에 따라 결과가 달라질 수 있으므로, 조건의 우선순위를 잘 고려해야 합니다.

## 한 줄 요약
Java의 `else` 문은 `if` 조건이 false일 때 실행될 코드를 정의하여 프로그램의 흐름을 제어하는 중요한 기능입니다.