<!--
Meta Description: # Java의 catch 키워드: 예외 처리의 기본 ## 개요 Java에서 `catch`는 예외 처리를 위한 중요한 키워드로, try 블록 내에서 발생할 수 있는 예외를 처리하는 데 사용됩니다. 이를 통해 프로그램의 안정성을 높이고, 예외 상황에 대한 적절한 대응을 할...
Meta Keywords: catch, try, 예외를, 있습니다, 블록에서
-->

# Java의 catch 키워드: 예외 처리의 기본

## 개요
Java에서 `catch`는 예외 처리를 위한 중요한 키워드로, try 블록 내에서 발생할 수 있는 예외를 처리하는 데 사용됩니다. 이를 통해 프로그램의 안정성을 높이고, 예외 상황에 대한 적절한 대응을 할 수 있습니다.

## 문서화
`catch`는 Java의 예외 처리 메커니즘의 일부로, `try` 블록에서 발생한 예외를 잡아내고 처리하는 역할을 합니다. 예외가 발생하면 Java는 실행을 중단하지 않고, `catch` 블록으로 제어를 이동시켜 해당 예외를 처리합니다.

### 목적
- 프로그램의 비정상 종료 방지
- 예외 발생 시 사용자에게 적절한 피드백 제공
- 코드의 안정성과 가독성 향상

### 사용법
`catch`는 일반적으로 `try` 블록과 함께 사용됩니다. `try` 블록에서 예외가 발생하면, 해당 예외에 맞는 `catch` 블록이 실행됩니다.

```java
try {
    // 예외가 발생할 수 있는 코드
} catch (예외타입 e) {
    // 예외 처리 코드
}
```

## 예시
다음은 `catch`를 사용하는 기본적인 예시입니다.

```java
public class CatchExample {
    public static void main(String[] args) {
        try {
            int result = 10 / 0; // ArithmeticException 발생
        } catch (ArithmeticException e) {
            System.out.println("0으로 나눌 수 없습니다: " + e.getMessage());
        }
    }
}
```

위의 코드에서, 0으로 나누기를 시도함으로써 `ArithmeticException`이 발생하고, `catch` 블록에서 해당 예외를 처리하여 오류 메시지를 출력합니다.

## 설명
`catch` 블록을 사용할 때 주의할 점은 다음과 같습니다:
- **다중 catch 블록**: 여러 개의 `catch` 블록을 사용하여 다양한 예외를 처리할 수 있습니다. 그러나, 더 구체적인 예외를 먼저 처리해야 합니다.
  
  ```java
  try {
      // 코드
  } catch (IOException e) {
      // IOException 처리
  } catch (Exception e) {
      // 일반 Exception 처리
  }
  ```

- **예외 전파**: `catch` 블록에서 예외를 처리한 후 다시 예외를 발생시키고 싶다면, `throw` 키워드를 사용할 수 있습니다.

- **finally 블록**: `try-catch` 구문과 함께 `finally` 블록을 사용하면, 예외 발생 여부와 관계없이 항상 실행되는 코드를 작성할 수 있습니다.

## 한 줄 요약
Java에서 `catch`는 try 블록 내에서 발생한 예외를 잡아내어 처리하는 키워드로, 프로그램의 안정성을 높이는 데 기여합니다.