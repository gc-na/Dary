<!--
Meta Description: # O que é "default" em Java: Compreendendo a Palavra-Chave ## Sinopse A palavra-chave "default" em Java é utilizada em diferentes contextos, principal...
Meta Keywords: default, switch, system, out, println
-->

# O que é "default" em Java: Compreendendo a Palavra-Chave

## Sinopse
A palavra-chave "default" em Java é utilizada em diferentes contextos, principalmente em interfaces e switch statements. Ela permite a implementação de métodos padrão em interfaces e designa um bloco de código que será executado se nenhuma das opções especificadas for atendida em uma estrutura switch.

## Documentação
### Propósito
O "default" serve para simplificar a implementação de interfaces e melhorar a legibilidade do código em estruturas de controle, como switch.

### Uso em Interfaces
Desde o Java 8, é possível definir métodos com implementação padrão em interfaces. Isso permite que interfaces evoluam sem quebrar a compatibilidade com as classes que já as implementam. Um método padrão é declarado usando a palavra-chave "default" seguida pela implementação do método.

**Exemplo:**
```java
interface Animal {
    void fazerSom();

    default void dormir() {
        System.out.println("O animal está dormindo.");
    }
}
```

### Uso em Switch Statements
Na estrutura switch, o "default" é usado para especificar um bloco de código que será executado quando nenhuma das condições especificadas nas cláusulas case for satisfeita. É uma maneira de lidar com situações inesperadas.

**Exemplo:**
```java
int dia = 5;

switch (dia) {
    case 1:
        System.out.println("Domingo");
        break;
    case 2:
        System.out.println("Segunda-feira");
        break;
    case 3:
        System.out.println("Terça-feira");
        break;
    case 4:
        System.out.println("Quarta-feira");
        break;
    case 5:
        System.out.println("Quinta-feira");
        break;
    default:
        System.out.println("Dia inválido");
}
```

## Exemplos
### Exemplo de Método Padrão em Interface
```java
class Cachorro implements Animal {
    @Override
    public void fazerSom() {
        System.out.println("Au Au");
    }
}
```
Neste exemplo, a classe `Cachorro` implementa a interface `Animal`, herdando o método `dormir()` como um comportamento padrão.

### Exemplo de Uso do Default em Switch
```java
String fruta = "maçã";

switch (fruta) {
    case "banana":
        System.out.println("Banana");
        break;
    case "laranja":
        System.out.println("Laranja");
        break;
    default:
        System.out.println("Fruta não reconhecida");
}
```
Aqui, se a variável `fruta` não corresponder a nenhum dos casos, a mensagem "Fruta não reconhecida" será exibida.

## Explicação
### Armadilhas Comuns
1. **Métodos Padrão em Interfaces**: Embora métodos padrão possam ser úteis, o uso excessivo pode levar a confusões, especialmente quando várias interfaces fornecem implementações para o mesmo método.
2. **Switch Statements**: Esquecer de adicionar um caso default pode resultar em comportamentos inesperados, pois não haverá um tratamento para entradas que não correspondem a nenhum caso.

### Notas Adicionais
- A palavra-chave "default" não deve ser confundida com o conceito de valores padrão em variáveis. Em interfaces, a implementação padrão é uma forma de encorajar a reutilização de código.
- É uma boa prática sempre incluir um bloco default em switch statements para garantir que todos os casos sejam tratados.

## Resumo em Uma Linha
A palavra-chave "default" em Java permite a definição de métodos padrão em interfaces e especifica um bloco de código em switch statements para tratar casos não especificados.