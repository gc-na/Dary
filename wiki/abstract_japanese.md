<!--
Meta Description: # Javaの抽象クラスと抽象メソッド：基本と応用 ## 概要 Javaにおける「abstract（抽象）」は、抽象クラスと抽象メソッドを定義するためのキーワードです。これにより、共通の基盤を持つクラスの設計が可能になります。 ## ドキュメンテーション ### 目的 抽象クラスは、一部のメソッドが...
Meta Keywords: abstract, void, class, shape, java
-->

# Javaの抽象クラスと抽象メソッド：基本と応用

## 概要
Javaにおける「abstract（抽象）」は、抽象クラスと抽象メソッドを定義するためのキーワードです。これにより、共通の基盤を持つクラスの設計が可能になります。

## ドキュメンテーション
### 目的
抽象クラスは、一部のメソッドが未実装のクラスを定義するために使用されます。これにより、他のクラスがこの抽象クラスを継承し、具体的な実装を提供することが求められます。抽象メソッドは、実装を持たないメソッドのことを指し、子クラスでの実装を強制します。

### 使用法
1. **抽象クラスの定義**:
   抽象クラスは、キーワード`abstract`を用いて定義します。抽象クラスは直接インスタンス化できません。

   ```java
   abstract class Animal {
       abstract void makeSound();
   }
   ```

2. **抽象メソッドの定義**:
   抽象メソッドも`abstract`キーワードを使用して宣言します。

   ```java
   abstract void makeSound();
   ```

3. **継承と実装**:
   子クラスは抽象クラスを継承し、抽象メソッドを実装する必要があります。

   ```java
   class Dog extends Animal {
       void makeSound() {
           System.out.println("Woof");
       }
   }
   ```

## 例
### 基本的な使用例

```java
abstract class Shape {
    abstract void draw();
}

class Circle extends Shape {
    void draw() {
        System.out.println("Circle drawn");
    }
}

class Main {
    public static void main(String[] args) {
        Shape shape = new Circle();
        shape.draw();  // Circle drawn
    }
}
```

## 説明
### 一般的な落とし穴
- **インスタンス化の禁止**: 抽象クラスは直接インスタンス化できないため、注意が必要です。
- **抽象メソッドの未実装**: 子クラスで抽象メソッドを実装しないと、コンパイルエラーが発生します。
- **多重継承の不可能性**: Javaでは、クラスは単一継承のみ可能であり、複数の抽象クラスを継承することができません。

### その他の注意点
- 抽象クラスはフィールドや非抽象メソッドを持つことも可能です。これにより、共通の動作を持たせることができます。
- インターフェースとは異なり、抽象クラスは状態を持つことができ、フィールドを定義することができます。

## 一行要約
Javaにおける「abstract」は、共通の基盤を持つクラス設計を可能にし、具体的な実装を子クラスに強制するための重要な機能です。