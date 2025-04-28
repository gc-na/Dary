<!--
Meta Description: # Java의 "requires" 키워드: 모듈 시스템의 핵심 ## 개요 Java의 "requires" 키워드는 Java 9에서 도입된 모듈 시스템의 중요한 구성 요소로, 모듈 간의 의존성을 정의하는 데 사용됩니다. 이 키워드는 특정 모듈이 다른 모듈에 의존하고 있음을...
Meta Keywords: requires, java, module, 모듈이, 있습니다
-->

# Java의 "requires" 키워드: 모듈 시스템의 핵심

## 개요
Java의 "requires" 키워드는 Java 9에서 도입된 모듈 시스템의 중요한 구성 요소로, 모듈 간의 의존성을 정의하는 데 사용됩니다. 이 키워드는 특정 모듈이 다른 모듈에 의존하고 있음을 명시하여, 모듈화된 애플리케이션의 품질과 유지 보수성을 향상시킵니다.

## 문서화
### 목적
"requires" 키워드는 Java 모듈 시스템에서 다른 모듈을 사용할 수 있도록 하는 의존성 선언을 제공합니다. 이를 통해 개발자는 애플리케이션의 모듈 간의 관계를 명확히 하고, 각 모듈이 필요로 하는 외부 모듈을 정의할 수 있습니다.

### 사용법
"requires" 키워드는 `module-info.java` 파일 내에서 사용되며, 다음과 같은 형식을 따릅니다:

```java
module moduleName {
    requires dependencyModuleName;
}
```

여기서 `moduleName`은 현재 모듈의 이름이며, `dependencyModuleName`은 의존하는 모듈의 이름입니다.

### 세부사항
- 여러 개의 모듈을 동시에 요구할 수 있습니다: 
  ```java
  module my.module {
      requires moduleA;
      requires moduleB;
  }
  ```
- 특정 모듈의 버전을 명시할 수도 있습니다:
  ```java
  module my.module {
      requires static moduleA;
  }
  ```
- `transitive` 키워드를 사용하여, 의존 모듈이 다른 모듈을 요구하는 경우에도 자동으로 해당 모듈을 포함시킬 수 있습니다:
  ```java
  module my.module {
      requires transitive moduleB;
  }
  ```

## 예제
아래는 "requires" 키워드를 사용하는 간단한 예제입니다.

### 기본 예제
```java
module myApplication {
    requires java.sql;
}
```
위의 예제에서 `myApplication` 모듈은 `java.sql` 모듈에 의존하고 있습니다.

### 여러 모듈 요구
```java
module myApp {
    requires moduleA;
    requires moduleB;
}
```
이 예제에서는 `myApp` 모듈이 `moduleA`와 `moduleB` 두 개의 모듈에 의존하고 있음을 나타냅니다.

## 설명
- **일반적인 함정**: "requires" 키워드를 사용할 때, 요구하는 모듈이 올바로 설정되어 있지 않으면 컴파일 오류가 발생할 수 있습니다. 따라서 의존성 모듈이 존재하는지 확인하는 것이 중요합니다.
- **모듈 경로**: "requires" 키워드를 사용한 모듈이 제대로 작동하려면, 모듈 경로가 올바르게 설정되어 있어야 합니다.
- **정적 요구**: "requires static"로 선언된 의존성은 런타임에 필요하지 않은 경우에 사용되며, 컴파일 타임에만 요구됩니다.

## 한 줄 요약
Java의 "requires" 키워드는 모듈 간의 의존성을 정의하여 모듈화된 애플리케이션의 구조적 품질을 향상시킵니다.