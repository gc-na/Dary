<!--
Meta Description: # Java의 return 문: 함수의 결과 반환하기 ## 개요 Java에서 `return` 문은 메서드나 함수의 실행을 종료하고, 선택적으로 값을 호출한 곳으로 반환하는 데 사용됩니다. 이 문은 메서드의 결과를 호출한 곳에 전달하며, 메서드의 흐름 제어를 관리하는 중...
Meta Keywords: return, 메서드의, int, public, void
-->

# Java의 return 문: 함수의 결과 반환하기

## 개요
Java에서 `return` 문은 메서드나 함수의 실행을 종료하고, 선택적으로 값을 호출한 곳으로 반환하는 데 사용됩니다. 이 문은 메서드의 결과를 호출한 곳에 전달하며, 메서드의 흐름 제어를 관리하는 중요한 역할을 합니다.

## 문서화

### 목적
`return` 문은 메서드의 결과를 반환하고, 메서드 실행을 종료하는 데 사용됩니다. 반환할 값의 유형은 메서드 선언 시 지정된 반환 타입에 따라 결정됩니다.

### 사용법
- 메서드의 반환 타입이 `void`인 경우: `return` 문을 사용하지 않거나, 단순히 `return;`을 사용하여 메서드를 종료할 수 있습니다.
- 메서드의 반환 타입이 특정 타입(예: int, String 등)인 경우: 해당 타입의 값을 `return` 문을 통해 반환해야 합니다.

```java
public int add(int a, int b) {
    return a + b; // 두 정수를 더한 결과를 반환
}
```

### 세부사항
- `return` 문이 실행되면, 메서드는 즉시 종료됩니다.
- 메서드의 반환 타입과 `return` 문에서 반환하는 값의 타입이 일치해야 합니다.
- `return` 문은 메서드의 마지막에 위치할 필요는 없으며, 조건문 내에서도 사용할 수 있습니다.

## 예제

### 간단한 예제
```java
public class Example {
    public static void main(String[] args) {
        int result = add(5, 3);
        System.out.println("Result: " + result);
    }

    public static int add(int a, int b) {
        return a + b; // a와 b를 더한 결과를 반환
    }
}
```

### void 반환 타입 예제
```java
public class Example {
    public static void main(String[] args) {
        printMessage();
    }

    public static void printMessage() {
        System.out.println("Hello, World!"); // 메시지를 출력
        return; // void 메서드에서는 return 문이 선택적
    }
}
```

## 설명
- **일치하는 타입**: `return` 문에서 반환하는 값의 타입은 메서드의 반환 타입과 일치해야 합니다. 일치하지 않는 경우 컴파일 오류가 발생합니다.
- **중복 호출 문제**: `return` 문이 메서드 내에서 여러 번 호출될 수 있지만, 실제로 메서드가 종료되는 시점은 첫 번째 `return` 문이 실행될 때입니다.
- **구조적 흐름**: `return` 문은 조건문이나 반복문 내에서 사용할 수 있지만, 메서드가 종료되는 것을 이해하고 사용하는 것이 중요합니다.

## 한 문장 요약
Java에서 `return` 문은 메서드의 실행을 종료하고, 선택적으로 값을 호출한 곳으로 반환하는 데 사용됩니다.