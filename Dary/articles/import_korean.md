<!--
Meta Description: # JAVA에서의 import 구문: 모듈화와 재사용성을 위한 필수 요소 ## 개요 JAVA에서 `import` 구문은 다른 클래스와 패키지를 코드에 포함시키기 위해 사용됩니다. 이 기능을 통해 개발자는 코드의 모듈화와 재사용성을 높일 수 있으며, 외부 라이브러리와 A...
Meta Keywords: import, java, list, 있습니다, 클래스를
-->

# JAVA에서의 import 구문: 모듈화와 재사용성을 위한 필수 요소

## 개요
JAVA에서 `import` 구문은 다른 클래스와 패키지를 코드에 포함시키기 위해 사용됩니다. 이 기능을 통해 개발자는 코드의 모듈화와 재사용성을 높일 수 있으며, 외부 라이브러리와 API를 쉽게 활용할 수 있습니다.

## 문서화
`import` 구문은 JAVA 프로그래밍에서 다른 패키지에 정의된 클래스, 인터페이스, 열거형 등을 현재 클래스에서 사용할 수 있도록 해줍니다. JAVA는 기본적으로 모든 클래스가 `java.lang` 패키지에 포함되어 있다고 가정하지만, 다른 패키지의 클래스를 사용하려면 명시적으로 `import` 구문을 사용해야 합니다.

### 사용법
- 기본 형식:
  ```java
  import 패키지이름.클래스이름;
  ```
- 특정 클래스가 아닌 모든 클래스를 가져올 때는 와일드카드(*)를 사용할 수 있습니다:
  ```java
  import 패키지이름.*;
  ```

이 구문은 주로 파일의 최상단에 위치하며, 여러 개의 클래스를 가져오려면 각 클래스에 대해 별도의 `import` 문을 작성하거나 와일드카드를 이용할 수 있습니다.

### 세부 사항
`import` 구문은 다음과 같은 주요 기능을 제공합니다:
- **패키지 접근**: JAVA의 패키지 시스템을 통해 코드의 구조를 정리하고 접근할 수 있도록 해줍니다.
- **코드 가독성 향상**: 클래스의 전체 경로를 매번 입력할 필요가 없어 코드가 간결해집니다.
- **충돌 방지**: 여러 패키지에서 동일한 이름의 클래스를 사용할 경우, 특정 클래스의 경로를 명시하여 충돌을 방지할 수 있습니다.

## 예제
1. 기본적인 `import` 사용 예:
   ```java
   import java.util.ArrayList;
   
   public class Main {
       public static void main(String[] args) {
           ArrayList<String> list = new ArrayList<>();
           list.add("Hello");
           System.out.println(list);
       }
   }
   ```

2. 와일드카드를 사용한 예:
   ```java
   import java.util.*;
   
   public class Main {
       public static void main(String[] args) {
           List<String> list = new ArrayList<>();
           list.add("Hello");
           System.out.println(list);
       }
   }
   ```

## 설명
- **일반적인 실수**: `import` 문을 잘못 사용할 경우, 클래스가 존재하지 않는다는 컴파일 오류가 발생할 수 있습니다. 패키지 이름이나 클래스 이름의 철자를 확인해야 합니다.
- **충돌**: 서로 다른 패키지에서 동일한 이름의 클래스를 가져올 경우, 컴파일러는 어떤 클래스를 사용할지 혼동할 수 있습니다. 이 경우, 전체 경로를 명시하는 것이 좋습니다.

## 한 줄 요약
JAVA의 `import` 구문은 다른 패키지의 클래스와 인터페이스를 코드에 포함시켜 모듈화와 재사용성을 높이는 기능입니다.