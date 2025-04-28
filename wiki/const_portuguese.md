<!--
Meta Description: # O Uso do "const" em Java: Entenda seu Propósito e Limitações ## Sinopse No Java, o termo "const" é frequentemente mal interpretado. Embora muitos pr...
Meta Keywords: final, que, java, não, ser
-->

# O Uso do "const" em Java: Entenda seu Propósito e Limitações

## Sinopse
No Java, o termo "const" é frequentemente mal interpretado. Embora muitos programadores venham de outras linguagens como C ou C++, onde "const" é uma palavra-chave, no Java, essa palavra não é utilizada. Este artigo explora os conceitos relacionados e alternativas disponíveis.

## Documentação
### Propósito
O Java não possui uma palavra-chave "const". Em vez disso, utiliza-se a palavra-chave `final` para declarar constantes. O uso do `final` assegura que uma variável não possa ser alterada após sua inicialização, promovendo a imutabilidade.

### Uso
Ao declarar uma variável como `final`, você a torna uma constante. Isso significa que, uma vez atribuída, seu valor não pode ser alterado. O `final` pode ser aplicado a variáveis, métodos e classes.

#### Sintaxe:
```java
final Tipo nomeVariavel = valor;
```

### Detalhes
- Para variáveis de instância e de classe, `final` implica que o valor não pode ser reatribuído.
- Para métodos, `final` impede que a função seja sobrescrita em subclasses.
- Para classes, `final` impede que a classe seja estendida.

## Exemplos
### Exemplo 1: Variável Final
```java
public class ExemploFinal {
    public static void main(String[] args) {
        final int numeroMaximo = 10;
        // numeroMaximo = 20; // Isto causaria um erro de compilação
        System.out.println("O número máximo é: " + numeroMaximo);
    }
}
```

### Exemplo 2: Método Final
```java
class ClasseBase {
    final void metodoFinal() {
        System.out.println("Este método não pode ser sobrescrito.");
    }
}

class ClasseDerivada extends ClasseBase {
    // void metodoFinal() { // Isto causaria um erro de compilação
    //     System.out.println("Tentativa de sobrescrever.");
    // }
}
```

### Exemplo 3: Classe Final
```java
final class ClasseFinal {
    // Implementação da classe
}

// class SubClasse extends ClasseFinal { // Isto causaria um erro de compilação
// }
```

## Explicação
Um erro comum entre desenvolvedores que vêm de outras linguagens é a suposição de que podem usar "const" no Java. Além disso, é importante notar que, ao usar `final`, você deve inicializar a variável na declaração ou no construtor, caso contrário, ocorrerá um erro de compilação. 

Outro ponto a ser observado é que `final` não implica necessariamente que o objeto em si seja imutável. Em vez disso, significa que a referência à instância do objeto não pode ser alterada. Portanto, as propriedades de um objeto final ainda podem ser modificadas se forem de um tipo mutável.

## Resumo em Uma Linha
No Java, a palavra-chave "const" não existe; utilize `final` para declarar constantes e impedir reatribuições.