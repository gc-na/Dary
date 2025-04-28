<!--
Meta Description: # Java의 switch 문: 효율적인 조건 분기 처리 ## 개요 Java의 `switch` 문은 변수의 값을 기반으로 여러 경우(case) 중 하나를 선택하여 실행할 수 있는 조건 분기 구조입니다. 이는 복잡한 if-else 문을 대체하여 코드의 가독성과 유지보수성...
Meta Keywords: switch, break, case, default, dayname
-->

# Java의 switch 문: 효율적인 조건 분기 처리

## 개요
Java의 `switch` 문은 변수의 값을 기반으로 여러 경우(case) 중 하나를 선택하여 실행할 수 있는 조건 분기 구조입니다. 이는 복잡한 if-else 문을 대체하여 코드의 가독성과 유지보수성을 높여 줍니다.

## 문서화

### 목적
`switch` 문은 정수형, 문자형, 문자열 및 열거형(enum) 타입의 변수를 검사하여 해당하는 경우에 따라 코드를 실행하는 데 사용됩니다. 이를 통해 다수의 조건을 간결하게 처리할 수 있습니다.

### 사용법
`switch` 문은 다음과 같은 형식으로 사용됩니다:

```java
switch (변수) {
    case 값1:
        // 실행할 코드 블록
        break;
    case 값2:
        // 실행할 코드 블록
        break;
    default:
        // 모든 case에 해당하지 않을 경우 실행할 코드 블록
        break;
}
```

- `변수`: 검사할 값입니다.
- `case`: 변수와 비교할 값입니다.
- `break`: 해당 case의 실행을 종료하고 switch 문을 빠져나옵니다. 생략할 경우, 다음 case로 이어서 실행됩니다.
- `default`: 모든 case에 해당하지 않을 경우 실행됩니다.

### 세부사항
- `switch` 문은 주로 조건이 명확한 경우에 사용됩니다.
- `break` 문을 사용하지 않으면 "fall-through" 현상이 발생하여 다음 case가 연속으로 실행될 수 있습니다.
- Java 7부터 문자열을 `switch` 문에서 사용할 수 있게 되었습니다.

## 예제

### 기본 사용 예제
```java
int day = 3;
String dayName;

switch (day) {
    case 1:
        dayName = "월요일";
        break;
    case 2:
        dayName = "화요일";
        break;
    case 3:
        dayName = "수요일";
        break;
    default:
        dayName = "주말";
        break;
}

System.out.println(dayName); // 출력: 수요일
```

### 문자열 사용 예제
```java
String fruit = "사과";
switch (fruit) {
    case "바나나":
        System.out.println("바나나입니다.");
        break;
    case "사과":
        System.out.println("사과입니다.");
        break;
    default:
        System.out.println("알 수 없는 과일입니다.");
        break;
}

// 출력: 사과입니다.
```

## 설명
`switch` 문을 사용할 때 주의해야 할 점은 다음과 같습니다:

- **fall-through**: `break` 문을 생략하면 다음 case가 실행됩니다. 이는 의도하지 않은 결과를 초래할 수 있으므로 주의가 필요합니다.
  
- **데이터 타입**: `switch` 문은 `byte`, `short`, `int`, `char`, `String`, 그리고 `enum` 타입에서 사용 가능합니다. 다른 타입에서는 사용할 수 없습니다.

- **default**: 모든 case에 해당하지 않는 값을 처리하기 위해 `default`를 작성하는 것이 좋습니다. 이를 통해 예외 상황을 처리할 수 있습니다.

## 한 줄 요약
Java의 `switch` 문은 여러 조건을 효율적으로 처리할 수 있는 조건 분기 구조로, 가독성과 유지보수성을 향상시킵니다.