<!--
Meta Description: # JAVA 패키지: Java에서 패키지의 이해와 활용 ## 개요 Java 패키지는 클래스와 인터페이스를 그룹화하여 코드의 구조를 체계적으로 관리하고, 이름 충돌을 방지하며, 접근 제어를 지원하는 기능입니다. 패키지를 사용하면 코드의 재사용성과 유지보수성을 높일 수 있...
Meta Keywords: java, 패키지, main, public, 패키지를
-->

# JAVA 패키지: Java에서 패키지의 이해와 활용

## 개요
Java 패키지는 클래스와 인터페이스를 그룹화하여 코드의 구조를 체계적으로 관리하고, 이름 충돌을 방지하며, 접근 제어를 지원하는 기능입니다. 패키지를 사용하면 코드의 재사용성과 유지보수성을 높일 수 있습니다.

## 문서화
Java에서 패키지는 관련된 클래스와 인터페이스를 논리적으로 모으는 데 사용됩니다. 패키지를 통해 다음과 같은 이점을 얻을 수 있습니다:

- **조직화**: 패키지는 관련 클래스들을 그룹화하여 코드의 구조를 명확히 합니다.
- **이름 충돌 방지**: 서로 다른 패키지에 동일한 이름의 클래스가 존재할 수 있어, 이름 충돌을 피할 수 있습니다.
- **접근 제어**: 패키지 내의 클래스는 같은 패키지 내에서만 접근할 수 있는 기본 접근 제어를 제공합니다.

### 패키지 선언
Java 클래스의 첫 번째 줄에 패키지 선언을 추가하여 클래스가 속하는 패키지를 정의합니다. 예를 들어:

```java
package com.example.myapp;
```

### 패키지 사용
패키지를 사용하려면 `import` 문을 통해 다른 패키지의 클래스를 가져와야 합니다. 예를 들어:

```java
import java.util.List;
import java.util.ArrayList;
```

## 예제
아래는 간단한 패키지 사용 예제입니다.

### 1. 패키지 선언과 클래스 정의

```java
// File: com/example/myapp/Main.java
package com.example.myapp;

public class Main {
    public static void main(String[] args) {
        System.out.println("Hello, Java Package!");
    }
}
```

### 2. 패키지에서 클래스 사용하기

```java
// File: com/example/myapp/AnotherClass.java
package com.example.myapp;

public class AnotherClass {
    public void displayMessage() {
        System.out.println("This is another class in the same package.");
    }
}
```

### 3. 외부 패키지 클래스 사용하기

```java
// File: Test.java
import com.example.myapp.Main;

public class Test {
    public static void main(String[] args) {
        Main.main(args); // Main 클래스의 main 메서드 호출
    }
}
```

## 설명
패키지를 사용할 때 몇 가지 주의해야 할 점이 있습니다:

- **패키지 이름 규칙**: 패키지 이름은 소문자로 시작해야 하며, 주로 도메인 이름의 역순을 사용하는 것이 일반적입니다.
- **접근 제어**: 기본 접근 제어를 사용할 때, 같은 패키지 내의 클래스에서만 접근 가능하므로, 필요한 경우 `public`, `protected`, `private` 키워드를 적절히 사용해야 합니다.
- **패키지 구조**: 프로젝트가 커질수록 패키지 구조를 잘 설계해야 코드 관리가 쉬워집니다. 일반적으로 기능별로 패키지를 나누는 것이 좋습니다.

## 한 줄 요약
Java 패키지는 클래스와 인터페이스를 그룹화하여 코드의 구조를 관리하고, 이름 충돌을 방지하는 중요한 기능입니다.