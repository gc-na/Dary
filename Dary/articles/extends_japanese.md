<!--
Meta Description: # Javaにおける「extends」の使い方と解説 ## 概要 Javaの「extends」は、クラスの継承を定義するために使用されるキーワードです。このキーワードを使うことで、既存のクラスから新しいクラスを派生させ、コードの再利用や拡張を容易にします。 ## ドキュメンテーション 「extend...
Meta Keywords: extends, class, void, dog, system
-->

# Javaにおける「extends」の使い方と解説

## 概要
Javaの「extends」は、クラスの継承を定義するために使用されるキーワードです。このキーワードを使うことで、既存のクラスから新しいクラスを派生させ、コードの再利用や拡張を容易にします。

## ドキュメンテーション
「extends」はJavaのクラス定義において、親クラス（スーパークラス）を指定するために使用されます。子クラス（サブクラス）は親クラスのプロパティやメソッドを引き継ぎ、さらに独自の特性を追加することができます。

### 目的
- コードの再利用: 既存のクラスの機能を再利用することで、開発の効率を向上させる。
- 拡張性: 基本的な機能を持つクラスを派生させて、特定の用途に適した新しいクラスを作成する。

### 使用法
```java
class SuperClass {
    void display() {
        System.out.println("This is the superclass.");
    }
}

class SubClass extends SuperClass {
    void show() {
        System.out.println("This is the subclass.");
    }
}
```
上記の例では、`SubClass`は`SuperClass`を継承しており、`SuperClass`のメソッド`display`を使用することができます。

## 例
以下は「extends」を用いた基本的な使用例です。

### 例1: シンプルな継承
```java
class Animal {
    void sound() {
        System.out.println("Animal makes a sound.");
    }
}

class Dog extends Animal {
    void sound() {
        System.out.println("Dog barks.");
    }
}

public class Test {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.sound(); // 出力: Dog barks.
    }
}
```

### 例2: メソッドのオーバーライド
```java
class Vehicle {
    void start() {
        System.out.println("Vehicle is starting.");
    }
}

class Car extends Vehicle {
    @Override
    void start() {
        System.out.println("Car is starting.");
    }
}

public class Test {
    public static void main(String[] args) {
        Vehicle myCar = new Car();
        myCar.start(); // 出力: Car is starting.
    }
}
```

## 説明
「extends」を使用する際の一般的な注意点や落とし穴があります。

- **多重継承の禁止**: Javaはクラスの多重継承をサポートしていません。すなわち、1つのクラスは1つの親クラスのみを持つことができます。
  
- **コンストラクタの呼び出し**: 子クラスのコンストラクタは、親クラスのコンストラクタを明示的に呼び出さない限り、親クラスのデフォルトコンストラクタを自動的に呼び出します。

- **親クラスのメソッドのオーバーライド**: 子クラスで親クラスのメソッドをオーバーライドする場合は、`@Override`アノテーションを使用することが推奨されます。これにより、オーバーライドが正しく行われているかコンパイラがチェックします。

## 一文要約
Javaの「extends」は、クラス間の継承を定義し、コードの再利用と拡張性を提供する重要なキーワードです。