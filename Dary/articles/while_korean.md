<!--
Meta Description: # Java의 while 문: 반복문 사용법 및 예제 ## 개요 Java에서 `while` 문은 조건이 참인 동안 특정 블록의 코드를 반복 실행할 수 있도록 해주는 제어 구조입니다. 주로 반복 횟수가 미리 정해지지 않았을 때 사용되며, 조건에 따라 실행 여부가 결정됩니...
Meta Keywords: while, 조건이, 합니다, scanner, system
-->

# Java의 while 문: 반복문 사용법 및 예제

## 개요
Java에서 `while` 문은 조건이 참인 동안 특정 블록의 코드를 반복 실행할 수 있도록 해주는 제어 구조입니다. 주로 반복 횟수가 미리 정해지지 않았을 때 사용되며, 조건에 따라 실행 여부가 결정됩니다.

## 문서화
`while` 문은 다음과 같은 형식으로 사용됩니다:

```java
while (조건) {
    // 반복 실행할 코드
}
```

### 목적
`while` 문은 주어진 조건이 참인 동안 반복적으로 실행되는 코드를 작성할 수 있게 해줍니다. 이는 사용자 입력 처리, 배열 탐색, 특정 조건이 충족될 때까지의 반복 작업 등 다양한 상황에서 유용하게 사용됩니다.

### 사용법
1. **조건**: `while` 문은 조건이 참인 경우에만 반복 실행됩니다. 조건이 거짓이 되면 반복이 종료됩니다.
2. **루프 바디**: 조건이 참일 때 실행될 코드 블록입니다. 이곳에서 변수를 업데이트하는 등의 작업을 통해 조건이 언젠가는 거짓이 되도록 해야 합니다.

### 세부 사항
- **무한 루프**: 조건이 항상 참인 경우, 루프는 끝나지 않고 계속 실행됩니다. 이는 시스템 자원을 소모할 수 있으므로 주의해야 합니다.
- **조건의 타입**: 조건은 불리언 표현식이어야 하며, 논리 연산자(`&&`, `||`, `!`)를 사용할 수 있습니다.
- **변수의 업데이트**: 루프 내부에서 조건을 변경할 수 있는 변수를 업데이트해야 합니다. 그렇지 않으면 무한 루프에 빠질 수 있습니다.

## 예제
### 기본 사용 예제

```java
public class WhileExample {
    public static void main(String[] args) {
        int i = 0;
        while (i < 5) {
            System.out.println("현재 i의 값: " + i);
            i++; // i를 증가시켜 조건이 거짓이 되도록 함
        }
    }
}
```

### 사용자 입력 처리 예제

```java
import java.util.Scanner;

public class UserInputExample {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String input;
        
        System.out.println("종료하려면 'exit'를 입력하세요.");
        while (true) {
            System.out.print("입력: ");
            input = scanner.nextLine();
            if (input.equals("exit")) {
                break; // 'exit'가 입력되면 루프 종료
            }
            System.out.println("입력한 값: " + input);
        }
        scanner.close();
    }
}
```

## 설명
- **무한 루프 방지**: `while` 문을 사용할 때는 조건이 항상 참인 경우를 피해야 합니다. 조건문을 올바르게 설정하고, 루프 안에서 조건을 변경하는 코드를 반드시 포함시켜야 합니다.
- **성능**: `while` 문은 반복 횟수가 가변적인 경우에 유용하지만, 반복이 너무 많아지면 성능 저하를 초래할 수 있습니다. 필요할 때 적절히 사용해야 합니다.
- **조건문**: 복잡한 조건문을 사용하여 루프의 실행을 더욱 세밀하게 제어할 수 있습니다. 

## 한 줄 요약
Java의 `while` 문은 주어진 조건이 참인 동안 특정 코드를 반복 실행하는 제어 구조입니다.