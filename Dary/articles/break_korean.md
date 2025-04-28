<!--
Meta Description: # Java의 break 명령어: 제어문에서의 사용 ## 개요 Java에서 `break` 명령어는 반복문이나 switch 문을 종료하는 데 사용됩니다. 이를 통해 프로그래머는 특정 조건에서 루프를 조기에 종료하거나 선택문을 빠져나올 수 있습니다. ## 문서화 `brea...
Meta Keywords: break, switch, system, out, println
-->

# Java의 break 명령어: 제어문에서의 사용

## 개요
Java에서 `break` 명령어는 반복문이나 switch 문을 종료하는 데 사용됩니다. 이를 통해 프로그래머는 특정 조건에서 루프를 조기에 종료하거나 선택문을 빠져나올 수 있습니다.

## 문서화
`break` 명령어는 Java 프로그래밍 언어에서 제어 흐름을 관리하는 중요한 기능입니다. 일반적으로 `for`, `while`, `do-while`와 같은 반복문 내에서 사용되며, 특정 조건이 충족될 때 루프를 종료하는 데 유용합니다. 또한, `switch` 문에서 특정 case 블록이 실행된 후 즉시 switch 문을 종료할 경우에도 사용됩니다.

### 사용법
- **반복문에서의 사용**: 반복문 내에서 `break`를 사용하면 해당 반복문을 즉시 종료합니다.
- **switch 문에서의 사용**: 각 case 블록의 끝에 `break`를 추가하여 다음 case로 넘어가지 않도록 할 수 있습니다.

### 문법
```java
break; // 반복문 또는 switch 문 종료
```

## 예제
### 1. 반복문에서의 사용
```java
for (int i = 0; i < 10; i++) {
    if (i == 5) {
        break; // i가 5일 때 루프 종료
    }
    System.out.println(i);
}
// 출력: 0, 1, 2, 3, 4
```

### 2. switch 문에서의 사용
```java
int day = 3;
switch (day) {
    case 1:
        System.out.println("월요일");
        break;
    case 2:
        System.out.println("화요일");
        break;
    case 3:
        System.out.println("수요일");
        break;
    default:
        System.out.println("주말");
}
// 출력: 수요일
```

## 설명
`break` 명령어를 사용할 때 주의해야 할 점은, 모든 반복문이나 switch 문에서 사용될 수 있지만, 잘못된 위치에 놓일 경우 코드의 흐름을 예기치 않게 변경할 수 있습니다. 특히 중첩된 루프에서 사용될 때, 가장 가까운 루프만 종료되므로, 원하는 결과가 아닐 수 있습니다. 이러한 경우 `break`에 레이블을 사용하여 특정 루프를 종료할 수 있습니다.

### 예제: 레이블을 사용한 break
```java
outerLoop: // 레이블 선언
for (int i = 0; i < 3; i++) {
    for (int j = 0; j < 3; j++) {
        if (i == 1 && j == 1) {
            break outerLoop; // outerLoop 레이블이 붙은 루프 종료
        }
        System.out.println("i: " + i + ", j: " + j);
    }
}
// 출력: i: 0, j: 0
//       i: 0, j: 1
//       i: 0, j: 2
//       i: 1, j: 0
//       i: 1, j: 1
```

## 한 문장 요약
Java의 `break` 명령어는 반복문이나 switch 문을 조기에 종료하는 데 사용되는 제어 흐름 명령어입니다.