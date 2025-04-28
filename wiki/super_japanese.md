<!--
Meta Description: # Javaにおける「super」キーワードの詳細ガイド ## 概要 「super」はJavaプログラミング言語において、親クラスのメンバー（フィールドやメソッド）にアクセスするために使用される特別なキーワードです。クラスの継承を利用する際に、親クラスの機能を再利用したり、オーバーライドしたメソッド...
Meta Keywords: super, parent, class, child, void
-->

# Javaにおける「super」キーワードの詳細ガイド

## 概要
「super」はJavaプログラミング言語において、親クラスのメンバー（フィールドやメソッド）にアクセスするために使用される特別なキーワードです。クラスの継承を利用する際に、親クラスの機能を再利用したり、オーバーライドしたメソッドを呼び出したりするために役立ちます。

## ドキュメンテーション
### 目的
「super」を使用することで、子クラスから親クラスのメンバーにアクセスし、親クラスの機能を利用することができます。これは、クラスの継承において非常に重要な概念です。

### 使用法
- **親クラスのフィールドへのアクセス**: 子クラスで同名のフィールドがある場合、`super`を使って親クラスのフィールドにアクセスできます。
- **親クラスのメソッドの呼び出し**: 子クラスでオーバーライドされたメソッドを呼び出す際に、`super`を使って元のメソッドを呼び出すことができます。
- **親クラスのコンストラクタの呼び出し**: 子クラスのコンストラクタ内で、`super()`を使って親クラスのコンストラクタを呼び出し、親クラスの初期化を行います。

### 詳細
- **フィールドへのアクセス**: 
  ```java
  class Parent {
      int value = 10;
  }

  class Child extends Parent {
      int value = 20;

      void display() {
          System.out.println("Child value: " + value); // 20
          System.out.println("Parent value: " + super.value); // 10
      }
  }
  ```

- **メソッドの呼び出し**:
  ```java
  class Parent {
      void show() {
          System.out.println("Parent show");
      }
  }

  class Child extends Parent {
      void show() {
          System.out.println("Child show");
      }

      void display() {
          show(); // Child show
          super.show(); // Parent show
      }
  }
  ```

- **コンストラクタの呼び出し**:
  ```java
  class Parent {
      Parent() {
          System.out.println("Parent constructor");
      }
  }

  class Child extends Parent {
      Child() {
          super(); // Parent constructorを呼び出す
          System.out.println("Child constructor");
      }
  }
  ```

## 例
以下のコードは「super」の基本的な使用例を示しています。

```java
class Animal {
    void sound() {
        System.out.println("Animal sound");
    }
}

class Dog extends Animal {
    void sound() {
        System.out.println("Dog barks");
    }

    void displaySound() {
        sound(); // Dog barks
        super.sound(); // Animal sound
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.displaySound();
    }
}
```

## 説明
「super」を使用する際の一般的な注意点には以下のようなものがあります。

- **名前の衝突**: 子クラスが親クラスと同名のフィールドやメソッドを持つ場合、明示的に`super`を使用しないと、子クラスのメンバーが参照されるため、注意が必要です。
- **コンストラクタの呼び出し**: `super()`を使用する場合、必ず子クラスの最初の行で呼び出す必要があります。そうしないと、コンパイルエラーになります。

## 一文要約
「super」はJavaにおいて、継承関係にある親クラスのメンバーにアクセスするための特別なキーワードです。