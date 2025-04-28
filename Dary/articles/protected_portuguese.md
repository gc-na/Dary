<!--
Meta Description: # Modificador de Acesso "protected" em Java: Entenda Como Funciona ## Sinopse O modificador de acesso `protected` em Java é um dos quatro níveis de ac...
Meta Keywords: protected, animal, que, public, acesso
-->

# Modificador de Acesso "protected" em Java: Entenda Como Funciona

## Sinopse
O modificador de acesso `protected` em Java é um dos quatro níveis de acesso que controlam a visibilidade de classes, métodos e variáveis. Ele permite o acesso a membros de uma classe por subclasses e classes no mesmo pacote.

## Documentação
O modificador `protected` é utilizado em Java para definir a visibilidade de métodos e variáveis de instância. Quando um membro é declarado como `protected`, ele pode ser acessado por:

1. **Subclasses**: Mesmo que estejam em pacotes diferentes.
2. **Classes do mesmo pacote**: Qualquer classe que pertença ao mesmo pacote pode acessar o membro `protected`.

### Propósito
O propósito do `protected` é facilitar a herança, permitindo que subclasses acessem membros da classe pai, enquanto ainda mantém um controle sobre quem pode acessar esses membros em comparação ao modificador `public`.

### Uso
Para declarar um membro como `protected`, você deve preceder a declaração com a palavra-chave `protected`. Aqui está um exemplo básico:

```java
public class Animal {
    protected String nome;

    protected void emitirSom() {
        System.out.println("O animal faz um som.");
    }
}
```

Neste exemplo, a variável `nome` e o método `emitirSom` são protegidos, permitindo acesso por subclasses e classes do mesmo pacote.

## Exemplos

### Exemplo 1: Acesso em Subclasses
```java
public class Animal {
    protected String nome;

    protected void emitirSom() {
        System.out.println("O animal faz um som.");
    }
}

public class Cachorro extends Animal {
    public void apresentar() {
        nome = "Rex"; // Acessando membro protegido da classe pai
        emitirSom(); // Chamando método protegido da classe pai
    }
}
```

### Exemplo 2: Acesso em Classes do Mesmo Pacote
```java
package zoologico;

public class Animal {
    protected String nome;

    protected void emitirSom() {
        System.out.println("O animal faz um som.");
    }
}

public class Gato {
    public void apresentar(Animal animal) {
        animal.nome = "Miau"; // Acessando membro protegido da classe Animal
        animal.emitirSom(); // Chamando método protegido da classe Animal
    }
}
```

## Explicação
Um ponto importante a ser considerado ao utilizar o modificador `protected` é que ele não é acessível de fora do pacote, a menos que seja através de uma subclasse. Isso pode levar a confusões, especialmente para desenvolvedores iniciantes que podem esperar que `protected` funcione como `public` em todos os contextos.

Além disso, o uso excessivo de `protected` pode resultar em um acoplamento maior entre classes, dificultando a manutenção do código. É aconselhável aplicar o modificador apenas quando necessário e quando a herança faz sentido.

## Resumo em Uma Linha
O modificador de acesso `protected` em Java permite que subclasses e classes do mesmo pacote acessem membros de classe, promovendo a reutilização de código através da herança.