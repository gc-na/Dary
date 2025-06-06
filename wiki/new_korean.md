<!--
Meta Description: # Java의 new 키워드: 객체 생성의 기본 ## 개요 Java에서 `new` 키워드는 객체를 생성하기 위해 사용되는 중요한 키워드입니다. 이 키워드는 클래스의 인스턴스를 만들고, 메모리에 할당하며, 생성자를 호출하는 역할을 합니다. ## 문서화 `new` 키워드는...
Meta Keywords: new, 클래스의, 키워드는, 객체를, dog
-->

# Java의 new 키워드: 객체 생성의 기본

## 개요
Java에서 `new` 키워드는 객체를 생성하기 위해 사용되는 중요한 키워드입니다. 이 키워드는 클래스의 인스턴스를 만들고, 메모리에 할당하며, 생성자를 호출하는 역할을 합니다.

## 문서화
`new` 키워드는 Java 프로그래밍에서 객체 지향 프로그래밍의 핵심 요소인 객체를 생성하는 데 필수적입니다. 사용자가 정의한 클래스의 인스턴스를 생성하고, 메모리 공간을 할당하고, 해당 클래스의 생성자를 호출하여 초기화합니다. 기본적인 사용법은 다음과 같습니다.

### 사용법
```java
ClassName objectName = new ClassName();
```
여기서 `ClassName`은 생성할 객체의 클래스 이름이며, `objectName`은 생성된 객체를 참조할 변수입니다. 

### 세부 사항
- `new` 키워드는 항상 클래스의 생성자와 함께 사용됩니다.
- 생성자는 객체를 초기화하는 데 필요한 코드를 포함하고 있으며, 해당 클래스의 구조에 따라 다양한 형태가 있을 수 있습니다.
- `new` 키워드로 생성된 객체는 힙 메모리에 저장됩니다.
- 객체가 더 이상 필요하지 않으면, 가비지 컬렉터가 자동으로 메모리를 회수합니다.

## 예제
### 기본 사용 예
```java
public class Dog {
    String name;

    Dog(String name) {
        this.name = name;
    }
}

public class Main {
    public static void main(String[] args) {
        Dog myDog = new Dog("Buddy"); // new 키워드를 사용하여 Dog 객체 생성
        System.out.println(myDog.name); // "Buddy" 출력
    }
}
```

### 배열 객체 생성 예
```java
int[] numbers = new int[5]; // new 키워드를 사용하여 정수 배열 생성
numbers[0] = 1;
numbers[1] = 2;
System.out.println(numbers[0]); // 1 출력
```

## 설명
`new` 키워드를 사용할 때 주의해야 할 몇 가지 사항이 있습니다:
- 생성자의 접근 제어자에 따라 객체 생성이 제한될 수 있습니다. private 생성자인 경우, 해당 클래스 외부에서 객체를 생성할 수 없습니다.
- `new` 키워드를 사용하여 생성된 객체는 자동으로 메모리에 할당되지만, 객체가 더 이상 필요하지 않을 때 가비지 컬렉터가 그것을 회수하도록 하는 메커니즘이 필요합니다.
- 배열과 같은 복합 데이터 타입도 `new` 키워드를 통해 생성할 수 있습니다.

## 한 줄 요약
Java의 `new` 키워드는 클래스의 인스턴스를 생성하고 초기화하는 데 사용되는 필수 키워드입니다.