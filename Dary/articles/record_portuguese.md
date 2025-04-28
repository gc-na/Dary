<!--
Meta Description: # Registros em JAVA: Entenda o Uso e as Vantagens ## Sinopse Registros (ou "records") em Java são uma funcionalidade introduzida no Java 14 como uma p...
Meta Keywords: registros, que, java, são, uma
-->

# Registros em JAVA: Entenda o Uso e as Vantagens

## Sinopse
Registros (ou "records") em Java são uma funcionalidade introduzida no Java 14 como uma prévia e consolidada na versão 16, que proporciona uma maneira concisa e clara de criar classes que são essencialmente contêineres de dados.

## Documentação
Os registros em Java têm como objetivo principal simplificar a criação de classes que apenas carregam dados. Eles fornecem uma maneira eficaz de declarar classes imutáveis e eliminam o boilerplate associado a getters, setters, `equals()`, `hashCode()`, e `toString()`. 

### Propósito
Os registros são utilizados para representar dados que têm um significado específico, onde a igualdade é baseada nos valores dos atributos e não na identidade da instância.

### Uso
Para definir um registro, utiliza-se a palavra-chave `record`, seguida pelo nome do registro e os parâmetros que ele deve conter, entre parênteses. Aqui está a sintaxe básica:

```java
record NomeDoRegistro(Tipo atributo1, Tipo atributo2) {}
```

### Detalhes
- Os registros são implicitamente `final`, o que significa que não podem ser estendidos.
- Todos os atributos declarados em um registro são automaticamente `private` e `final`.
- O compilador gera automaticamente métodos `equals()`, `hashCode()`, e `toString()`.
- Os registros suportam herança de interface, podendo implementar múltiplas interfaces.

## Exemplos
### Exemplo Básico
Aqui está um exemplo simples de como declarar e usar um registro:

```java
public record Pessoa(String nome, int idade) {}

public class Main {
    public static void main(String[] args) {
        Pessoa pessoa = new Pessoa("João", 30);
        System.out.println(pessoa.nome());  // Saída: João
        System.out.println(pessoa.idade()); // Saída: 30
    }
}
```

### Exemplo com Método Personalizado
Os registros também podem conter métodos personalizados:

```java
public record Retangulo(double largura, double altura) {
    public double area() {
        return largura * altura;
    }
}

public class Main {
    public static void main(String[] args) {
        Retangulo retangulo = new Retangulo(5.0, 3.0);
        System.out.println("Área: " + retangulo.area()); // Saída: Área: 15.0
    }
}
```

## Explicação
Um dos principais erros ao trabalhar com registros é tentar estendê-los, pois como mencionado, eles são finais. Além disso, como os registros são imutáveis, não é possível modificar seus atributos após a criação. Outro ponto a ser observado é que, embora os registros sejam uma maneira conveniente de encapsular dados, eles não devem ser usados para representar entidades complexas que possuem comportamento significativo. Em tais casos, é preferível usar classes tradicionais.

## Resumo em Uma Linha
Registros em Java são uma forma simplificada de definir classes imutáveis que encapsulam dados, automatizando a criação de métodos comuns.