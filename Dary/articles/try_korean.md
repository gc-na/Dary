<!--
Meta Description: # Java의 try 문: 예외 처리를 위한 필수 도구 ## 개요 Java의 `try` 문은 프로그램 실행 중 발생할 수 있는 예외를 처리하기 위한 구조입니다. 예외 처리는 프로그램의 안정성과 신뢰성을 높이는 중요한 요소로, `try` 문을 사용하여 예외 발생 시 적절...
Meta Keywords: try, 예외를, catch, java, 발생할
-->

# Java의 try 문: 예외 처리를 위한 필수 도구

## 개요
Java의 `try` 문은 프로그램 실행 중 발생할 수 있는 예외를 처리하기 위한 구조입니다. 예외 처리는 프로그램의 안정성과 신뢰성을 높이는 중요한 요소로, `try` 문을 사용하여 예외 발생 시 적절한 대응을 할 수 있습니다.

## 문서화

### 목적
`try` 문은 코드 블록 내에서 발생할 수 있는 예외를 감지하고 처리하여 프로그램의 비정상 종료를 방지합니다. 이를 통해 개발자는 예외가 발생할 경우에 대한 대처 로직을 작성할 수 있습니다.

### 사용법
Java에서 `try` 문은 다음과 같은 형식을 가집니다:

```java
try {
    // 예외가 발생할 가능성이 있는 코드
} catch (ExceptionType e) {
    // 예외 발생 시 처리할 코드
} finally {
    // 항상 실행되는 코드 (선택 사항)
}
```

- **try 블록**: 예외가 발생할 수 있는 코드를 포함합니다.
- **catch 블록**: 특정 예외를 처리하는 코드입니다. 여러 개의 `catch` 블록을 사용하여 다양한 예외를 처리할 수 있습니다.
- **finally 블록**: 예외 발생 여부와 관계없이 항상 실행되는 코드를 포함합니다. 주로 자원 해제 등의 작업에서 사용됩니다.

### 세부 사항
- `try` 문은 여러 개의 `catch` 블록을 가질 수 있으며, 각 `catch` 블록은 처리할 특정 예외의 타입을 명시합니다.
- `finally` 블록은 선택적이며, 예외가 발생하든 발생하지 않든 항상 실행됩니다.
- `try-with-resources` 구문을 사용하면 자동으로 자원을 해제할 수 있어, 파일 처리와 같은 자원 관리에서 유용합니다.

## 예제

### 기본 사용 예
```java
public class TryExample {
    public static void main(String[] args) {
        try {
            int result = 10 / 0; // 예외 발생
        } catch (ArithmeticException e) {
            System.out.println("0으로 나눌 수 없습니다.");
        }
    }
}
```

### try-with-resources 예제
```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class TryWithResourcesExample {
    public static void main(String[] args) {
        try (BufferedReader br = new BufferedReader(new FileReader("file.txt"))) {
            String line;
            while ((line = br.readLine()) != null) {
                System.out.println(line);
            }
        } catch (IOException e) {
            System.out.println("파일 읽기 중 오류가 발생했습니다.");
        }
    }
}
```

## 설명
`try` 문을 사용할 때 주의해야 할 점은 다음과 같습니다:

- **예외 전파**: catch 블록에서 예외를 처리하지 않으면, 예외는 호출 스택을 따라 상위 호출자에게 전파됩니다. 이로 인해 프로그램이 비정상적으로 종료될 수 있으므로, 적절한 예외 처리가 필요합니다.
- **모든 예외 처리**: 모든 예외를 처리하지 않고 무시하는 것은 좋지 않습니다. 예외를 적절히 처리하거나 로깅하여 문제를 추적할 수 있도록 해야 합니다.
- **성능 고려**: 예외 처리는 성능에 영향을 미칠 수 있으므로, 자주 발생하는 상황에서는 예외를 피하는 것이 좋습니다.

## 한 줄 요약
Java의 `try` 문은 예외 처리를 위한 필수 구조로, 오류 발생 시 프로그램의 안정성을 보장합니다.