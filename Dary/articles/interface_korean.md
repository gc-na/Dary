<!--
Meta Description: # 자바 인터페이스: 개념과 활용 ## 개요 자바 인터페이스는 클래스가 구현해야 하는 메서드의 집합을 정의하는 특수한 참조형입니다. 이는 객체 지향 프로그래밍의 다형성을 지원하며, 여러 클래스가 동일한 메서드를 구현할 수 있도록 합니다. ## 문서화 ### 목적 자바 ...
Meta Keywords: public, void, animal, makesound, 인터페이스는
-->

# 자바 인터페이스: 개념과 활용

## 개요
자바 인터페이스는 클래스가 구현해야 하는 메서드의 집합을 정의하는 특수한 참조형입니다. 이는 객체 지향 프로그래밍의 다형성을 지원하며, 여러 클래스가 동일한 메서드를 구현할 수 있도록 합니다.

## 문서화
### 목적
자바 인터페이스의 주된 목적은 다양한 클래스에서 공통적으로 사용되는 메서드의 계약을 정의하는 것입니다. 이를 통해 코드의 재사용성을 높이고, 다른 클래스 간의 결합도를 낮추어 유연성을 증가시킵니다.

### 사용법
인터페이스는 `interface` 키워드를 사용하여 정의됩니다. 인터페이스에 선언된 모든 메서드는 기본적으로 `public`이며, 구현할 클래스에서 반드시 오버라이드해야 합니다. 

```java
public interface Animal {
    void makeSound();
}
```

클래스가 인터페이스를 구현하기 위해서는 `implements` 키워드를 사용합니다. 

```java
public class Dog implements Animal {
    @Override
    public void makeSound() {
        System.out.println("멍멍!");
    }
}

public class Cat implements Animal {
    @Override
    public void makeSound() {
        System.out.println("야옹!");
    }
}
```

### 세부사항
- 인터페이스는 다중 상속을 지원합니다. 하나의 클래스는 여러 개의 인터페이스를 구현할 수 있습니다.
- 인터페이스는 상수 필드를 가질 수 있으며, 모든 필드는 자동으로 `public static final`입니다.
- 자바 8부터는 인터페이스에 기본 메서드(가장 기본적인 구현을 제공하는 메서드)를 정의할 수 있습니다.

```java
public interface Vehicle {
    void drive();
    
    default void honk() {
        System.out.println("빵빵!");
    }
}
```

## 예제
다음은 인터페이스를 사용하여 다양한 동물 클래스를 구현하는 간단한 예제입니다.

```java
public interface Animal {
    void makeSound();
}

public class Dog implements Animal {
    @Override
    public void makeSound() {
        System.out.println("멍멍!");
    }
}

public class Cat implements Animal {
    @Override
    public void makeSound() {
        System.out.println("야옹!");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal dog = new Dog();
        Animal cat = new Cat();
        
        dog.makeSound(); // 출력: 멍멍!
        cat.makeSound(); // 출력: 야옹!
    }
}
```

## 설명
자바 인터페이스를 사용할 때 주의해야 할 점은 다음과 같습니다:
- 인터페이스는 구현 클래스에서 반드시 모든 메서드를 구현해야 하므로, 누락된 메서드가 있는 경우 컴파일 오류가 발생합니다.
- 인터페이스는 다중 상속을 지원하지만, 일반 클래스는 단일 상속만 지원하므로 이를 적절히 활용해야 합니다.
- 인터페이스가 변경되면 이를 구현하는 모든 클래스에 영향을 미치므로, 인터페이스 설계 시 신중해야 합니다.

## 한 줄 요약
자바 인터페이스는 클래스가 구현해야 할 메서드의 계약을 정의하며, 코드의 재사용성과 유연성을 높이는 데 기여합니다.