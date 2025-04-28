<!--
Meta Description: # Java에서의 "super" 키워드 이해하기 ## 개요 Java에서 "super" 키워드는 상속 관계에서 부모 클래스의 멤버(변수나 메서드)에 접근할 때 사용되는 특별한 키워드입니다. 이를 통해 자식 클래스에서 부모 클래스의 속성과 행동을 명확히 식별하고 활용할 수...
Meta Keywords: 클래스의, super, name, child, parent
-->

# Java에서의 "super" 키워드 이해하기

## 개요
Java에서 "super" 키워드는 상속 관계에서 부모 클래스의 멤버(변수나 메서드)에 접근할 때 사용되는 특별한 키워드입니다. 이를 통해 자식 클래스에서 부모 클래스의 속성과 행동을 명확히 식별하고 활용할 수 있습니다.

## 문서화
"super" 키워드는 Java의 객체 지향 프로그래밍(OOP)에서 중요한 역할을 합니다. 주로 다음과 같은 용도로 사용됩니다:

1. **부모 클래스의 생성자 호출**: 자식 클래스에서 부모 클래스의 생성자를 호출할 때 사용합니다.
2. **부모 클래스의 메서드 호출**: 자식 클래스에서 부모 클래스의 메서드를 오버라이드 했을 때, 부모 클래스의 원래 메서드를 호출하기 위해 사용합니다.
3. **부모 클래스의 변수 접근**: 자식 클래스에서 부모 클래스의 멤버 변수를 참조할 때 사용합니다.

### 사용법
- 부모 클래스의 생성자 호출: `super();`
- 부모 클래스의 메서드 호출: `super.methodName();`
- 부모 클래스의 변수 접근: `super.variableName;`

## 예제
다음은 "super" 키워드를 사용하는 간단한 예제입니다.

```java
class Parent {
    String name;

    Parent(String name) {
        this.name = name;
    }

    void display() {
        System.out.println("부모 클래스: " + name);
    }
}

class Child extends Parent {
    
    Child(String name) {
        super(name); // 부모 클래스의 생성자 호출
    }
    
    void display() {
        super.display(); // 부모 클래스의 메서드 호출
        System.out.println("자식 클래스: " + name);
    }
}

public class Main {
    public static void main(String[] args) {
        Child child = new Child("홍길동");
        child.display();
    }
}
```

이 예제에서는 `Parent` 클래스와 `Child` 클래스가 있으며, `Child` 클래스는 `Parent` 클래스의 생성자와 메서드를 호출하는 데 "super" 키워드를 사용합니다.

## 설명
"super" 키워드를 사용할 때 주의해야 할 몇 가지 사항이 있습니다:

- **명확한 구분**: 자식 클래스와 부모 클래스 모두에 같은 이름의 변수나 메서드가 있을 경우, "super"를 사용하여 명확히 부모 클래스의 것을 참조해야 합니다.
- **생성자 호출 순서**: 자식 클래스의 생성자가 호출되기 전에 반드시 부모 클래스의 생성자가 먼저 호출되어야 합니다. 이를 통해 부모 클래스의 초기화가 이루어집니다.
- **정적 메서드와의 혼동**: "super"는 인스턴스 메서드에만 사용되며, 정적 메서드에서는 사용할 수 없습니다.

## 한 줄 요약
Java에서 "super" 키워드는 상속 관계에서 부모 클래스의 멤버에 접근하기 위해 사용되는 키워드입니다.