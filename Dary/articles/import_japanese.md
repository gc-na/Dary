<!--
Meta Description: # Javaにおける「import」文の徹底ガイド ## 概要 Javaプログラミング言語における「import」文は、他のクラスやパッケージをプログラム内で使用するための命令です。この機能を利用することで、必要な機能やクラスを簡潔に呼び出し、コードの可読性を向上させることができます。 ## ドキュ...
Meta Keywords: import, java, static, area, public
-->

# Javaにおける「import」文の徹底ガイド

## 概要
Javaプログラミング言語における「import」文は、他のクラスやパッケージをプログラム内で使用するための命令です。この機能を利用することで、必要な機能やクラスを簡潔に呼び出し、コードの可読性を向上させることができます。

## ドキュメント
### 目的
「import」文は、Javaで定義されたクラスやパッケージを他のクラスに読み込むために使用されます。これにより、フルパスを指定することなく、他のクラスの機能を利用できるようになります。

### 使用法
「import」文は、クラスファイルの先頭部分に記述します。一般的な構文は以下の通りです。

```java
import パッケージ名.クラス名;
```

また、特定のパッケージ内のすべてのクラスをインポートする場合は、アスタリスク（*）を使用します。

```java
import パッケージ名.*;
```

### 詳細
- **パッケージのインポート**: Javaのクラスは、パッケージにグループ化されており、同じパッケージ内にあるクラスは自動的にアクセス可能ですが、異なるパッケージにあるクラスを使用する場合、「import」文が必要です。
- **デフォルトパッケージ**: クラスがデフォルトパッケージに属している場合、他のパッケージからそのクラスをインポートすることはできません。
- **静的インポート**: 静的メンバー（メソッドやフィールド）をインポートすることも可能です。これにより、クラス名を指定せずに静的メンバーを直接使用できます。

```java
import static パッケージ名.クラス名.メソッド名;
```

## 例
以下に「import」文の基本的な使用例を示します。

```java
// java.utilパッケージからArrayListクラスをインポート
import java.util.ArrayList;

public class Example {
    public static void main(String[] args) {
        // ArrayListのインスタンスを作成
        ArrayList<String> list = new ArrayList<>();
        list.add("Hello");
        list.add("World");
        System.out.println(list);
    }
}
```

静的インポートの例:

```java
import static java.lang.Math.PI;
import static java.lang.Math.sqrt;

public class Circle {
    public static void main(String[] args) {
        double radius = 5;
        double area = PI * radius * radius;
        System.out.println("Area: " + area);
        System.out.println("Square root of area: " + sqrt(area));
    }
}
```

## 説明
- **一般的な落とし穴**: 同名のクラスが異なるパッケージに存在する場合、どちらのクラスをインポートするかで混乱が生じることがあります。この場合、フルパスを使用することで解決できます。
- **未使用のインポート**: IDEによっては、未使用のインポート文があると警告が表示されることがあります。これにより、コードをクリーンに保つことができます。
- **循環インポート**: 複数のクラスが互いにインポートし合うと、循環依存が発生することがあります。これはコンパイルエラーの原因になります。

## 一文要約
Javaにおける「import」文は、他のクラスやパッケージを参照可能にするための重要な機能です。