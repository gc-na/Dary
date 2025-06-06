<!--
Meta Description: # Javaにおける「non-sealed」キーワードの解説 ## 概要 Javaの「non-sealed」キーワードは、クラスやインターフェースの階層での拡張を制御するための機能です。Java 15で導入され、特にsealedクラスと組み合わせて使用されます。このキーワードを使うことで、特定のクラ...
Meta Keywords: sealed, non, class, dog, extends
-->

# Javaにおける「non-sealed」キーワードの解説

## 概要
Javaの「non-sealed」キーワードは、クラスやインターフェースの階層での拡張を制御するための機能です。Java 15で導入され、特にsealedクラスと組み合わせて使用されます。このキーワードを使うことで、特定のクラスの拡張を許可し、より強い設計を促進することができます。

## ドキュメンテーション
### 目的
「non-sealed」は、sealedクラスのサブクラスとして定義されたクラスが、さらにその下にサブクラスを持つことを許可するために使用されます。これにより、拡張性を持ちながらも、基本的な設計の意図を守ることができます。

### 使用法
「non-sealed」キーワードは、以下のようにクラス定義に追加します。

```java
non-sealed class SubClass extends SealedClass {
    // 実装
}
```

このようにすることで、`SubClass`は他のクラスから拡張されることができます。

### 詳細
- **前提条件**: `non-sealed`は`sealed`クラスのサブクラスとしてのみ使用できます。
- **制限**: `non-sealed`クラスは、他のクラスから自由に拡張可能ですが、そのクラスが持つ制約や設計意図に注意する必要があります。
- **使用ケース**: 特定のドメインモデルやAPI設計において、拡張を許可したいが、全体の構造を維持したい場合に有効です。

## 例
以下は、`sealed`クラスと`non-sealed`クラスの基本的な使用例です。

```java
sealed class Animal permits Dog, Cat {
}

non-sealed class Dog extends Animal {
    // Dogの実装
}

class Cat extends Animal {
    // Catの実装
}

class Bulldog extends Dog {
    // Bulldogの実装
}
```

この例では、`Animal`は`Dog`と`Cat`のみを許可し、`Dog`はさらに自由に拡張可能です。

## 説明
### 一般的な落とし穴
- **設計意図の混乱**: `non-sealed`を使用することで、クラスの拡張性が高まりますが、設計意図が複雑になる可能性があります。使用する場合は、意図を明確にすることが重要です。
- **パフォーマンスの考慮**: 多くの階層構造を持つクラスは、パフォーマンスに影響を与える可能性があります。適切に設計された階層を維持することが重要です。

### 追加の注意点
- `non-sealed`クラスは、他の`sealed`クラスのサブクラスとして定義する必要があります。この点を理解しておくことが重要です。
- `non-sealed`を使うことで、クラスの拡張を許可しますが、他の開発者との連携を考慮し、コードの可読性を損なわないように心掛けましょう。

## 一文要約
Javaにおける「non-sealed」キーワードは、sealedクラスのサブクラスとして定義され、その下にさらなる拡張を許可するための強力な機能です。