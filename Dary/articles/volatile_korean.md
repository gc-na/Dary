<!--
Meta Description: # Java의 volatile 키워드: 멀티스레드 환경에서의 변수 접근 제어 ## 개요 Java의 `volatile` 키워드는 멀티스레드 환경에서 변수의 가시성을 보장하고, 스레드 간의 일관성을 유지하기 위해 사용되는 중요한 키워드입니다. `volatile`로 선언된 ...
Meta Keywords: volatile, counter, public, 멀티스레드, 키워드는
-->

# Java의 volatile 키워드: 멀티스레드 환경에서의 변수 접근 제어

## 개요
Java의 `volatile` 키워드는 멀티스레드 환경에서 변수의 가시성을 보장하고, 스레드 간의 일관성을 유지하기 위해 사용되는 중요한 키워드입니다. `volatile`로 선언된 변수는 여러 스레드에 의해 동시에 접근될 수 있으며, 각 스레드는 항상 최신 값을 읽어올 수 있습니다.

## 문서화

### 목적
`volatile` 키워드는 스레드 간의 메모리 가시성을 보장하여, 하나의 스레드에서 변경된 값이 다른 스레드에서 즉시 반영되도록 하는 역할을 합니다. 이는 멀티스레드 프로그래밍에서 발생할 수 있는 오류를 줄이는 데 도움을 줍니다.

### 사용법
변수를 `volatile`로 선언하면, 해당 변수를 사용하는 스레드는 항상 메인 메모리에서 최신 값을 읽고, 값을 변경할 때도 메인 메모리에 즉시 반영됩니다. 다음은 `volatile` 키워드의 사용법입니다:

```java
public class VolatileExample {
    private volatile boolean flag = false;

    public void setFlagTrue() {
        flag = true;
    }

    public boolean isFlag() {
        return flag;
    }
}
```

### 세부 사항
- `volatile` 변수는 캐시 메모리에서 유지되지 않으며, 항상 메인 메모리에서 값을 읽고 씁니다.
- `volatile`은 원자성을 보장하지 않기 때문에, 복합 연산(예: 증가 연산)에는 적합하지 않습니다. 이러한 경우 `synchronized` 블록이나 `Lock`을 사용해야 합니다.

## 예제

### 기본 사용 예제

```java
public class VolatileCounter {
    private volatile int counter = 0;

    public void increment() {
        counter++;
    }

    public int getCounter() {
        return counter;
    }
}

public class Main {
    public static void main(String[] args) throws InterruptedException {
        VolatileCounter counter = new VolatileCounter();
        
        Thread t1 = new Thread(() -> {
            for (int i = 0; i < 1000; i++) {
                counter.increment();
            }
        });

        Thread t2 = new Thread(() -> {
            for (int i = 0; i < 1000; i++) {
                counter.increment();
            }
        });

        t1.start();
        t2.start();
        t1.join();
        t2.join();

        System.out.println("Counter: " + counter.getCounter());
    }
}
```

## 설명
- `volatile` 키워드는 스레드 간의 가시성을 보장하지만, 원자성을 보장하지 않기 때문에 주의가 필요합니다. 예를 들어, `counter++`와 같은 연산은 원자적이지 않으므로 여러 스레드가 동시에 접근할 경우 예상치 못한 결과가 발생할 수 있습니다.
- `volatile`은 메모리 성능에 영향을 미칠 수 있으므로, 필요할 때만 사용하는 것이 좋습니다.

## 한 줄 요약
Java의 `volatile` 키워드는 멀티스레드 환경에서 변수의 가시성을 보장하여 스레드 간의 일관성을 유지하는 데 사용된다.