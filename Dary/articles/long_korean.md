<!--
Meta Description: # Java의 long 데이터 타입: 이해와 활용 ## 개요 Java에서 `long`은 64비트의 정수형 데이터 타입으로, 매우 큰 정수를 표현하는 데 사용됩니다. `long`은 기본 데이터 타입 중 하나로, 숫자 범위가 넓어 다양한 수치 계산에 유용합니다. ## 문서...
Meta Keywords: long, 데이터, int, public, 타입은
-->

# Java의 long 데이터 타입: 이해와 활용

## 개요
Java에서 `long`은 64비트의 정수형 데이터 타입으로, 매우 큰 정수를 표현하는 데 사용됩니다. `long`은 기본 데이터 타입 중 하나로, 숫자 범위가 넓어 다양한 수치 계산에 유용합니다.

## 문서화

### 목적
`long` 데이터 타입은 정수 값을 저장하기 위해 사용되며, 일반적인 `int` 타입보다 더 큰 범위의 숫자를 처리할 수 있습니다. 이는 예를 들어, 큰 데이터 집합이나 고급 수치 연산이 필요한 경우에 유용합니다.

### 사용법
`long` 타입은 다음과 같이 선언할 수 있습니다:

```java
long myLongValue = 100000L; // L을 붙여서 리터럴을 long으로 명시
```

### 상세 설명
- **범위**: `long`의 값은 -9,223,372,036,854,775,808에서 9,223,372,036,854,775,807까지입니다.
- **기본값**: `long`의 기본값은 0L입니다.
- **리터럴**: `long` 리터럴은 숫자 뒤에 `L` 또는 `l`을 붙여서 선언해야 합니다. 대문자 `L`을 사용하는 것이 좋습니다. 소문자 `l`은 숫자 1과 혼동될 수 있습니다.
- **형변환**: `int`를 `long`으로 변환할 때는 자동 형변환이 이루어지지만, 반대의 경우에는 명시적 형변환이 필요합니다.

## 예제

### 기본 사용 예
```java
public class LongExample {
    public static void main(String[] args) {
        long largeNumber = 1234567890123L; // long 타입 변수 선언
        System.out.println("큰 숫자: " + largeNumber);
    }
}
```

### 형변환 예
```java
public class LongConversion {
    public static void main(String[] args) {
        int intValue = 100;
        long longValue = intValue; // 자동 형변환
        System.out.println("int를 long으로 변환: " + longValue);
    }
}
```

## 설명
- **일반적인 실수**: `long` 타입을 사용할 때 `L` 접미사를 잊지 않는 것이 중요합니다. 이를 생략하면 컴파일 오류가 발생합니다.
- **메모리 사용**: `long`은 `int`보다 더 많은 메모리를 사용하므로, 필요한 경우에만 사용하는 것이 좋습니다. 
- **계산 성능**: `long`을 사용하는 수치 연산은 `int`보다 느릴 수 있으므로, 성능이 중요한 경우 `int`를 고려해야 합니다.

## 한 줄 요약
Java의 `long` 데이터 타입은 64비트 정수를 저장할 수 있는 기본 데이터 타입으로, 대규모 숫자 처리를 가능하게 합니다.