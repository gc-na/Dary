<!--
Meta Description: # 자바의 Sealed 클래스 및 인터페이스: 제어 가능한 상속 ## 개요 자바의 "sealed" 기능은 클래스와 인터페이스의 상속을 제어하여, 특정 클래스나 인터페이스만이 상속할 수 있도록 제한하는 방법입니다. 이는 코드의 가독성과 유지보수성을 높이며, 상속 구조를 ...
Meta Keywords: sealed, 클래스, 상속을, 클래스를, non
-->

# 자바의 Sealed 클래스 및 인터페이스: 제어 가능한 상속

## 개요
자바의 "sealed" 기능은 클래스와 인터페이스의 상속을 제어하여, 특정 클래스나 인터페이스만이 상속할 수 있도록 제한하는 방법입니다. 이는 코드의 가독성과 유지보수성을 높이며, 상속 구조를 명확하게 정의할 수 있게 도와줍니다.

## 문서화
### 목적
Sealed 클래스와 인터페이스는 상속을 제한하고, 특정 서브클래스만 허용함으로써, 개발자가 의도한 디자인을 강제할 수 있습니다. 이 기능은 자바 15에서 미리 보기로 도입되었으며, 자바 17에서 정식으로 확정되었습니다.

### 사용법
Sealed 클래스를 정의할 때는 `sealed`, `non-sealed`, `final` 키워드를 사용할 수 있습니다.

- **sealed**: 이 키워드는 클래스나 인터페이스가 다른 클래스에 의해 상속될 수 있지만, 특정 클래스만을 허용할 것임을 나타냅니다.
- **permits**: 어떤 서브클래스가 상속할 수 있는지를 명시합니다.
- **non-sealed**: 이 키워드는 상속을 제한하지 않으며, 해당 클래스는 다른 모든 클래스에 의해 상속될 수 있습니다.
- **final**: 이 키워드는 해당 클래스를 더 이상 상속할 수 없게 만듭니다.

### 예제
```java
// Sealed 클래스 정의
public sealed class Shape permits Circle, Square {
    // 클래스 내용
}

public final class Circle extends Shape {
    // Circle 클래스 내용
}

public final class Square extends Shape {
    // Square 클래스 내용
}

// non-sealed 클래스 정의
public non-sealed class Triangle extends Shape {
    // Triangle 클래스 내용
}

// Triangle 클래스는 다른 클래스에 의해 상속될 수 있음
public class IsoscelesTriangle extends Triangle {
    // IsoscelesTriangle 클래스 내용
}
```

## 설명
Sealed 클래스를 사용할 때 주의해야 할 점은 상속 구조가 복잡해질 수 있다는 것입니다. 따라서, 상속을 허용하는 클래스는 신중하게 선택해야 하며, `permits` 키워드를 통해 명확하게 정의해야 합니다. 또한, 각 서브클래스는 `final` 또는 `non-sealed`로 정의하여 상속 구조를 명확히 해야 합니다.

### 일반적인 실수 및 주의사항
- **잘못된 상속**: Sealed 클래스를 상속받는 서브클래스가 `permits`에 정의되지 않은 경우 컴파일 오류가 발생합니다.
- **명확한 의도**: 상속을 허용할 클래스와 하지 않을 클래스를 명확히 구분해야, 의도하지 않은 상속이 발생하지 않습니다.
- **가독성 유지**: 너무 많은 서브클래스를 허용하게 되면 코드의 가독성이 떨어질 수 있으므로, 필요할 때만 사용해야 합니다.

## 요약
자바의 Sealed 클래스 및 인터페이스 기능은 상속을 제한하여 코드의 구조와 가독성을 개선하는 데 도움을 줍니다.