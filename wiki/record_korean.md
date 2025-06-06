<!--
Meta Description: # 자바의 레코드(Record): 간결한 데이터 클래스를 위한 혁신 ## 개요 자바의 레코드는 간단한 데이터 구조를 정의하기 위해 도입된 기능으로, 데이터 중심의 프로그래밍을 효율적으로 지원합니다. 레코드는 불변 객체를 생성하는 데 유용하며, 데이터 클래스의 작성 시 ...
Meta Keywords: 레코드는, 데이터, person, record, public
-->

# 자바의 레코드(Record): 간결한 데이터 클래스를 위한 혁신

## 개요
자바의 레코드는 간단한 데이터 구조를 정의하기 위해 도입된 기능으로, 데이터 중심의 프로그래밍을 효율적으로 지원합니다. 레코드는 불변 객체를 생성하는 데 유용하며, 데이터 클래스의 작성 시 boilerplate 코드를 줄여줍니다.

## 문서화
레코드는 자바 14에서 미리보기 기능으로 도입되었으며, 자바 16에서 정식으로 추가되었습니다. 레코드는 `record` 키워드를 사용하여 선언됩니다. 레코드를 사용하면 데이터 필드와 관련된 기본 메서드(예: `equals()`, `hashCode()`, `toString()`)가 자동으로 생성됩니다.

### 목적
레코드는 주로 다음과 같은 목적을 가지고 있습니다:
- 데이터 전송 객체(DTO)를 간단하게 정의하기 위함
- 불변 데이터 구조를 쉽게 생성하기 위함
- 코드의 가독성을 높이고 유지보수를 용이하게 하기 위함

### 사용법
레코드는 다음과 같은 형식으로 선언합니다:

```java
public record RecordName(Type field1, Type field2) {}
```

여기서 `RecordName`은 레코드의 이름이며, `field1`, `field2`는 레코드가 포함할 데이터 필드입니다.

## 예제
간단한 레코드 예제입니다.

```java
public record Person(String name, int age) {}

public class Main {
    public static void main(String[] args) {
        Person person = new Person("홍길동", 30);
        System.out.println(person.name()); // 출력: 홍길동
        System.out.println(person.age());  // 출력: 30
    }
}
```

위의 예제에서 `Person` 레코드는 이름과 나이를 속성으로 가지며, 해당 속성에 접근하기 위한 메서드가 자동으로 생성됩니다.

## 설명
레코드를 사용할 때 주의해야 할 몇 가지 사항이 있습니다:
- 레코드는 불변 객체입니다. 즉, 레코스가 생성된 후에는 필드 값을 변경할 수 없습니다.
- 레코드는 반드시 `final` 속성을 가져야 하며, 상속을 지원하지 않습니다.
- 레코드는 표준 JavaBeans와는 다르게 getter 메서드가 필드 이름과 동일한 이름을 가집니다.

레코드를 사용할 때는 데이터 클래스의 간결함과 효율성을 극대화할 수 있지만, 불변성의 제약으로 인해 변경 가능한 속성이 필요한 경우에는 일반 클래스를 사용하는 것이 더 적합할 수 있습니다.

## 한 줄 요약
자바의 레코드는 간단하고 불변의 데이터 클래스를 정의하기 위한 기능으로, boilerplate 코드를 줄이고 코드 가독성을 향상시킵니다.