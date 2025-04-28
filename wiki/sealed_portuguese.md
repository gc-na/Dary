<!--
Meta Description: # Sealed Classes e Interfaces em Java: Entendendo o Novo Recurso do Java 15 ## Sinopse As classes e interfaces seladas (sealed) introduzidas no Java 1...
Meta Keywords: classes, public, classe, que, uma
-->

# Sealed Classes e Interfaces em Java: Entendendo o Novo Recurso do Java 15

## Sinopse
As classes e interfaces seladas (sealed) introduzidas no Java 15 permitem que desenvolvedores limitem quais classes podem estender ou implementar suas estruturas. Este recurso é fundamental para garantir a integridade do modelo de dados e a segurança do tipo, proporcionando um controle mais rigoroso sobre a hierarquia de classes.

## Documentação
As classes e interfaces seladas são um novo recurso da linguagem Java que tem como principal objetivo permitir um controle mais refinado sobre a herança. Com o uso de classes seladas, os desenvolvedores podem especificar quais classes têm permissão para herdar de uma classe ou implementar uma interface específica.

### Propósito
O propósito das classes e interfaces seladas é fornecer uma maneira de restringir a herança, aumentando a segurança do tipo e permitindo que os desenvolvedores definam hierarquias de classes mais claras e gerenciáveis.

### Uso
Para declarar uma classe ou interface como selada, utiliza-se a palavra-chave `sealed`, seguida por uma lista de classes que podem estendê-la. As classes que estendem uma classe selada devem ser declaradas como `final`, `sealed` ou `non-sealed`.

### Sintaxe
```java
public sealed class NomeClasse permits ClassePermitida1, ClassePermitida2 {
    // corpo da classe
}

public final class ClassePermitida1 extends NomeClasse {
    // corpo da classe
}

public sealed class ClassePermitida2 extends NomeClasse permits ClassePermitida3 {
    // corpo da classe
}

public final class ClassePermitida3 extends ClassePermitida2 {
    // corpo da classe
}
```

## Exemplos
### Exemplo Básico de Classe Selada
```java
public sealed class Animal permits Dog, Cat {
    // corpo da classe
}

public final class Dog extends Animal {
    // corpo da classe
}

public final class Cat extends Animal {
    // corpo da classe
}
```

### Exemplo Básico de Interface Selada
```java
public sealed interface Shape permits Circle, Square {
    double area();
}

public final class Circle implements Shape {
    private final double radius;

    public Circle(double radius) {
        this.radius = radius;
    }

    @Override
    public double area() {
        return Math.PI * radius * radius;
    }
}

public final class Square implements Shape {
    private final double side;

    public Square(double side) {
        this.side = side;
    }

    @Override
    public double area() {
        return side * side;
    }
}
```

## Explicação
Um dos principais desafios ao utilizar classes e interfaces seladas é garantir que todas as classes permitidas sejam corretamente declaradas. Além disso, as classes que estendem uma classe selada devem ser declaradas como `final` se não desejarem permitir mais extensões, o que pode levar a confusões se não for bem entendido.

Além disso, ao usar classes e interfaces seladas, é importante lembrar que se uma classe selada não tem permissão para ser estendida por outra, isso pode limitar a flexibilidade no design do sistema. Portanto, a decisão de usar classes seladas deve ser feita com cuidado, considerando as necessidades de manutenção e expansão futura do código.

## Resumo em Uma Linha
As classes e interfaces seladas em Java permitem um controle rigoroso sobre a herança, garantindo que apenas classes específicas possam estender ou implementar uma determinada estrutura.