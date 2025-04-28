<!--
Meta Description: # Java의 "non-sealed" 키워드: 비봉인 클래스와 인터페이스 ## 개요 Java에서 "non-sealed" 키워드는 Java 17에서 도입된 새로운 기능으로, 클래스나 인터페이스가 서브타입으로 확장될 수 있도록 허용합니다. 이 키워드는 클래스의 서브클래스에...
Meta Keywords: sealed, non, 클래스를, 키워드는, public
-->

# Java의 "non-sealed" 키워드: 비봉인 클래스와 인터페이스

## 개요
Java에서 "non-sealed" 키워드는 Java 17에서 도입된 새로운 기능으로, 클래스나 인터페이스가 서브타입으로 확장될 수 있도록 허용합니다. 이 키워드는 클래스의 서브클래스에 대한 제한을 해제하여 더욱 유연한 상속 구조를 제공합니다.

## 문서화

### 목적
"non-sealed" 키워드는 기존의 sealed 클래스와 인터페이스와 결합하여, 해당 클래스나 인터페이스의 하위 유형을 정의할 수 있는 자유로운 구조를 제공합니다. 이는 하위 클래스나 인터페이스가 필요할 때 유용합니다.

### 사용법
"non-sealed" 키워드는 sealed 클래스 또는 인터페이스의 하위 클래스를 정의할 때 사용됩니다. 사용 예시는 다음과 같습니다:

```java
// sealed 클래스 선언
public sealed class Animal permits Dog, Cat {
}

// non-sealed 클래스 선언
public non-sealed class Dog extends Animal {
}

// 또 다른 non-sealed 클래스 선언
public non-sealed class Cat extends Animal {
}
```

위의 예제에서, `Animal` 클래스는 `Dog`와 `Cat` 클래스만 하위 클래스로 허용하지만, `Dog`와 `Cat` 클래스는 자유롭게 추가적인 하위 클래스를 정의할 수 있습니다.

### 세부사항
- `sealed`: 특정 클래스나 인터페이스의 하위 클래스를 제한할 수 있습니다.
- `non-sealed`: 해당 클래스의 하위 클래스를 무제한으로 정의할 수 있도록 허용합니다.
- `permits`: 이 키워드는 `sealed` 클래스를 확장할 수 있는 클래스 목록을 정의합니다.

## 예제
다음은 "non-sealed" 키워드의 기본적인 사용 예입니다:

```java
public sealed class Shape permits Circle, Square {
}

public non-sealed class Circle extends Shape {
}

public non-sealed class Square extends Shape {
}

public class Triangle extends Circle {
    // Triangle은 Circle의 하위 클래스입니다.
}
```

위의 코드에서 `Shape`는 `Circle`과 `Square`만 허용하지만, `Circle`은 추가적으로 `Triangle`이라는 하위 클래스를 가질 수 있습니다.

## 설명
- **일반적인 오류**: "non-sealed" 클래스를 사용할 때, 해당 클래스의 상위 클래스가 `sealed`로 선언되어 있어야만 의미가 있습니다. 만약 상위 클래스가 `non-sealed`거나 `final`이라면, "non-sealed" 키워드는 필요하지 않습니다.
- **가다듬기**: `non-sealed` 클래스를 정의하여 하위 클래스를 자유롭게 만들 수 있지만, 너무 많은 하위 클래스를 생성할 경우 코드의 복잡성이 증가할 수 있습니다.
- **추가 메모**: "non-sealed"는 하위 클래스의 정의를 제한하지 않기 때문에, 상속을 통해 보다 다양한 구현을 가능하게 합니다. 

## 한 줄 요약
Java의 "non-sealed" 키워드는 클래스나 인터페이스가 하위 클래스를 자유롭게 정의할 수 있도록 허용하는 기능입니다.