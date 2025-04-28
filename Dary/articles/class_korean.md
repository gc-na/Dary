<!--
Meta Description: # JAVA 클래스: 객체 지향 프로그래밍의 핵심 ## 개요 JAVA에서 클래스는 객체 지향 프로그래밍(OOP)의 기본 구성 요소로, 객체의 속성과 행동을 정의하는 틀입니다. 클래스는 코드의 재사용성을 높이고, 프로그램을 구조적으로 잘 조직할 수 있게 해줍니다. ## ...
Meta Keywords: public, 클래스, 클래스는, model, java
-->

# JAVA 클래스: 객체 지향 프로그래밍의 핵심

## 개요
JAVA에서 클래스는 객체 지향 프로그래밍(OOP)의 기본 구성 요소로, 객체의 속성과 행동을 정의하는 틀입니다. 클래스는 코드의 재사용성을 높이고, 프로그램을 구조적으로 잘 조직할 수 있게 해줍니다.

## 문서화
클래스는 JAVA에서 객체를 생성하기 위한 청사진 역할을 합니다. 클래스 내부에는 변수(필드)와 메서드(행동)가 포함되어 있으며, 이를 통해 객체의 상태와 동작을 정의합니다. 클래스는 다음과 같은 목적과 사용법이 있습니다:

- **목적**: 클래스는 객체를 생성하고, 해당 객체의 속성과 행동을 명세합니다. 이를 통해 코드의 모듈성을 높이고, 유지 보수를 용이하게 만듭니다.
- **사용법**: 클래스를 정의하기 위해 `class` 키워드를 사용하며, 클래스 이름은 대문자로 시작하는 것이 일반적입니다. 클래스 내부에는 필드와 메서드를 정의할 수 있습니다.

```java
public class Dog {
    // 필드
    String name;
    int age;

    // 생성자
    public Dog(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // 메서드
    public void bark() {
        System.out.println(name + "가 짖습니다!");
    }
}
```

## 예제
아래는 기본적인 JAVA 클래스의 예입니다.

```java
public class Car {
    // 필드
    String model;
    int year;

    // 생성자
    public Car(String model, int year) {
        this.model = model;
        this.year = year;
    }

    // 메서드
    public void displayInfo() {
        System.out.println("모델: " + model + ", 연도: " + year);
    }
}

public class Main {
    public static void main(String[] args) {
        Car myCar = new Car("Tesla Model S", 2022);
        myCar.displayInfo(); // 출력: 모델: Tesla Model S, 연도: 2022
    }
}
```

## 설명
클래스를 사용할 때 주의해야 할 몇 가지 사항이 있습니다:

1. **클래스 이름 규칙**: 클래스 이름은 대문자로 시작해야 하며, CamelCase 형태를 따르는 것이 좋습니다.
2. **다중 상속 불가**: JAVA는 다중 상속을 지원하지 않으므로, 하나의 클래스는 하나의 부모 클래스만 가질 수 있습니다.
3. **접근 제어자**: 클래스와 그 내부 요소에 대한 접근 제어자를 적절히 설정해야 합니다. 기본적으로 필드는 `private`, 메서드는 `public`으로 설정하는 것이 일반적입니다.
4. **정적 메서드**: 클래스 내부에 `static` 키워드를 사용하여 정적 메서드를 정의할 수 있으며, 이는 객체 생성 없이 호출할 수 있습니다.

## 한 줄 요약
JAVA 클래스는 객체의 속성과 행동을 정의하는 객체 지향 프로그래밍의 기본 구조입니다.