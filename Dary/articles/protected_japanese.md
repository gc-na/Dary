<!--
Meta Description: # Javaの「protected」アクセス修飾子について ## 概要 Javaにおける「protected」は、クラスのメンバーに対するアクセス制御を提供するためのアクセス修飾子です。この修飾子を使用することで、同じパッケージ内のクラスや、異なるパッケージに属するサブクラスからメンバーにアクセスで...
Meta Keywords: protected, class, void, public, child
-->

# Javaの「protected」アクセス修飾子について

## 概要
Javaにおける「protected」は、クラスのメンバーに対するアクセス制御を提供するためのアクセス修飾子です。この修飾子を使用することで、同じパッケージ内のクラスや、異なるパッケージに属するサブクラスからメンバーにアクセスできるようになります。

## ドキュメンテーション
### 目的
「protected」修飾子は、クラスのフィールドやメソッドが他のクラスからどのようにアクセスされるかを制御します。特に、サブクラスからのアクセスを許可することで、オブジェクト指向プログラミングにおける継承の概念をサポートします。

### 使用法
- **定義**: クラスのメンバー（フィールドやメソッド）の前に「protected」キーワードを付けて宣言します。
- **アクセスの範囲**:
  - 同じパッケージに属するクラスからのアクセスを許可
  - 異なるパッケージに属するサブクラスからのアクセスを許可
- **特徴**: 
  - 「protected」修飾子を使用したメンバーは、publicやprivateと異なり、特定の制限付きでアクセスが可能です。

## 例
以下は、「protected」修飾子を使用した基本的な例です。

### 例1: 基本的な使用法
```java
class Parent {
    protected void display() {
        System.out.println("親クラスからのメッセージ");
    }
}

class Child extends Parent {
    public void show() {
        display(); // 親クラスのprotectedメソッドにアクセス
    }
}

public class Main {
    public static void main(String[] args) {
        Child child = new Child();
        child.show(); // 出力: 親クラスからのメッセージ
    }
}
```

### 例2: 同じパッケージ内でのアクセス
```java
package mypackage;

class Base {
    protected void greet() {
        System.out.println("こんにちは");
    }
}

class Derived extends Base {
    public void sayHello() {
        greet(); // 同じパッケージ内でアクセス可能
    }
}

public class Main {
    public static void main(String[] args) {
        Derived derived = new Derived();
        derived.sayHello(); // 出力: こんにちは
    }
}
```

## 説明
### 一般的な落とし穴
- **異なるパッケージのクラスからアクセス不可**: 「protected」メンバーは、同じパッケージにいるクラスからはアクセスできますが、異なるパッケージにいる非サブクラスからはアクセスできません。
- **サブクラスのインスタンスでのアクセス**: サブクラスのインスタンスを使って親クラスの「protected」メンバーにアクセスする際、継承関係を理解しておくことが重要です。

### 追加の注意点
- **interface**: インターフェース内のメンバーはデフォルトでpublicなので、「protected」は使えません。
- **abstractクラス**: 抽象クラスでは「protected」メンバーを定義することができ、サブクラスで実装できます。

## 一行要約
Javaの「protected」修飾子は、同じパッケージや異なるパッケージのサブクラスからアクセス可能なメンバーを定義するためのアクセス制御の手段です。