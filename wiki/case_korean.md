<!--
Meta Description: # 자바의 switch-case 문: 효율적인 조건 분기 ## 개요 자바의 `switch-case` 문은 여러 조건 중 하나를 선택하여 실행할 수 있는 제어 구조로, 복잡한 if-else 문을 대체할 수 있는 간결한 방법을 제공합니다. 주로 정수형, 문자, 문자열 등의...
Meta Keywords: case, break, switch, dayname, default
-->

# 자바의 switch-case 문: 효율적인 조건 분기

## 개요
자바의 `switch-case` 문은 여러 조건 중 하나를 선택하여 실행할 수 있는 제어 구조로, 복잡한 if-else 문을 대체할 수 있는 간결한 방법을 제공합니다. 주로 정수형, 문자, 문자열 등의 값을 기반으로 조건을 분기하는 데 사용됩니다.

## 문서화
### 목적
`switch-case` 문은 여러 개의 조건을 간단하게 처리할 수 있도록 설계되었습니다. 코드의 가독성을 높이고, 특정 값에 따라 다른 코드를 실행할 수 있게 해줍니다.

### 사용법
자바에서 `switch-case` 문은 다음의 구문 형식을 가집니다:

```java
switch (expression) {
    case value1:
        // value1에 대한 실행 코드
        break;
    case value2:
        // value2에 대한 실행 코드
        break;
    // 추가적인 case 문들...
    default:
        // 어떤 case에도 해당하지 않을 경우 실행될 코드
}
```

- **expression**: 평가할 변수 또는 표현식입니다.
- **case**: 비교할 값입니다. 각 case는 독립적으로 실행될 수 있습니다.
- **break**: 해당 case의 실행을 마치고 switch 문을 종료합니다. break 문이 없으면 다음 case로 계속 실행됩니다.
- **default**: 모든 case에 해당하지 않을 때 실행되는 코드입니다.

## 예제
다음은 `switch-case` 문을 사용하는 간단한 예제입니다:

```java
public class SwitchCaseExample {
    public static void main(String[] args) {
        int day = 3;
        String dayName;

        switch (day) {
            case 1:
                dayName = "일요일";
                break;
            case 2:
                dayName = "월요일";
                break;
            case 3:
                dayName = "화요일";
                break;
            case 4:
                dayName = "수요일";
                break;
            case 5:
                dayName = "목요일";
                break;
            case 6:
                dayName = "금요일";
                break;
            case 7:
                dayName = "토요일";
                break;
            default:
                dayName = "유효하지 않은 날";
                break;
        }

        System.out.println(dayName); // 화요일
    }
}
```

## 설명
- `switch-case` 문을 사용할 때 주의해야 할 점은 `break` 문이 없으면 코드가 다음 case로 계속해서 실행된다는 점입니다. 이를 "fall-through" 현상이라고 합니다. 이러한 현상은 의도적으로 사용할 수 있지만, 주의가 필요합니다.
- 자바 12부터는 `switch` 표현식을 사용할 수 있으며, 이는 더 간결한 문법을 제공합니다. 예를 들어:

```java
String dayName = switch (day) {
    case 1 -> "일요일";
    case 2 -> "월요일";
    case 3 -> "화요일";
    case 4 -> "수요일";
    case 5 -> "목요일";
    case 6 -> "금요일";
    case 7 -> "토요일";
    default -> "유효하지 않은 날";
};
```

## 한 문장 요약
자바의 `switch-case` 문은 여러 조건을 효율적으로 처리할 수 있는 제어 구조로, 코드의 가독성을 높이고 간결하게 조건 분기를 수행할 수 있게 해줍니다.