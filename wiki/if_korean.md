<!--
Meta Description: # 자바의 "if" 문: 조건문을 통한 흐름 제어 ## 개요 자바에서 "if" 문은 조건에 따라 프로그램의 흐름을 제어하는 데 사용되는 중요한 제어 구조입니다. 조건이 참인 경우 특정 코드 블록을 실행하고, 그렇지 않은 경우 다른 코드 블록을 실행할 수 있도록 해줍니다...
Meta Keywords: else, 조건이, 있습니다, 실행할, 숫자는
-->

# 자바의 "if" 문: 조건문을 통한 흐름 제어

## 개요
자바에서 "if" 문은 조건에 따라 프로그램의 흐름을 제어하는 데 사용되는 중요한 제어 구조입니다. 조건이 참인 경우 특정 코드 블록을 실행하고, 그렇지 않은 경우 다른 코드 블록을 실행할 수 있도록 해줍니다.

## 문서화
### 목적
"if" 문은 프로그램의 실행 흐름을 조건에 따라 다르게 만들 수 있는 기능을 제공합니다. 이를 통해 프로그래머는 다양한 상황에 맞춰 프로그램을 유연하게 구성할 수 있습니다.

### 사용법
자바에서 "if" 문은 다음과 같은 형식으로 사용됩니다:

```java
if (조건) {
    // 조건이 true일 때 실행할 코드
} else {
    // 조건이 false일 때 실행할 코드 (선택 사항)
}
```

- **조건**: boolean 값을 반환하는 표현식. 조건이 참(true)일 경우, 중괄호 안의 코드 블록이 실행됩니다.
- **else**: 선택적 부분으로, 조건이 거짓(false)일 경우 실행할 코드 블록을 정의합니다.

### 세부사항
- "if" 문은 중첩될 수 있어, 여러 조건을 검사할 수 있습니다.
- "else if"를 사용하여 여러 조건을 순차적으로 검사할 수 있습니다.

```java
if (조건1) {
    // 조건1이 true일 때 실행
} else if (조건2) {
    // 조건2가 true일 때 실행
} else {
    // 둘 다 false일 때 실행
}
```

## 예시
아래는 "if" 문을 사용하는 기본적인 예시입니다.

```java
public class IfExample {
    public static void main(String[] args) {
        int number = 10;

        if (number > 0) {
            System.out.println("숫자는 양수입니다.");
        } else if (number < 0) {
            System.out.println("숫자는 음수입니다.");
        } else {
            System.out.println("숫자는 0입니다.");
        }
    }
}
```

### 출력
```
숫자는 양수입니다.
```

## 설명
- **일반적인 오류**: 조건 표현식이 boolean 값을 반환하지 않거나, 스코프를 잘못 설정하여 의도한 대로 코드가 실행되지 않을 수 있습니다.
- **중첩 if 문**: 중첩된 "if" 문을 사용할 때, 코드가 복잡해질 수 있으므로 주의해야 합니다. 코드의 가독성을 높이기 위해 적절한 주석을 추가하는 것이 좋습니다.
- **삼항 연산자**: 간단한 조건문은 삼항 연산자를 사용하여 더욱 간결하게 표현할 수 있습니다.

## 한 줄 요약
자바의 "if" 문은 조건에 따른 실행 흐름 제어를 가능하게 하여, 프로그램의 유연성을 높이는 중요한 기능입니다.