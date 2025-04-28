<!--
Meta Description: # Non-Sealed no Java: Entenda a Nova Abordagem de Herança ## Sinopse O modificador "non-sealed" no Java é uma nova característica introduzida no Java ...
Meta Keywords: classe, sealed, classes, que, non
-->

# Non-Sealed no Java: Entenda a Nova Abordagem de Herança

## Sinopse
O modificador "non-sealed" no Java é uma nova característica introduzida no Java 17 que permite que classes seladas (sealed classes) sejam estendidas por classes não seladas, oferecendo maior flexibilidade na herança.

## Documentação
O recurso de classes seladas foi introduzido no Java 15 como uma forma de controlar quais classes podem herdar de uma classe base. O modificador "non-sealed" é uma extensão desse conceito, permitindo que uma classe não selada herde de uma classe selada, sem restrições adicionais.

### Propósito
O objetivo do "non-sealed" é proporcionar uma maneira de permitir que subclasses de uma classe selada sejam abertas para extensões em um nível mais amplo, permitindo que desenvolvedores criem hierarquias de classes mais flexíveis e menos restritivas.

### Uso
Para declarar uma classe como "non-sealed", você deve usar a palavra-chave `non-sealed` antes da definição da classe. Essa classe pode herdar de uma classe selada e pode ser estendida por qualquer outra classe, permitindo um grau de liberdade maior na sua utilização.

### Detalhes
- **Compatibilidade:** O uso de "non-sealed" é compatível apenas com classes que foram declaradas como seladas (sealed).
- **Limitações:** Uma classe não selada não pode ser utilizada como uma classe selada.
- **Uso em hierarquias de classes:** Ideal para cenários onde você deseja permitir extensões em um conjunto de classes restrito, mas ainda manter algum controle sobre heranças.

## Exemplos
Aqui estão alguns exemplos básicos que demonstram como usar a palavra-chave "non-sealed":

### Exemplo 1: Definição Básica de Classes
```java
// Classe selada
public sealed class Animal permits Dog, Cat {
}

// Classe não selada que herda da classe selada
public non-sealed class Dog extends Animal {
}

// Classe que estende a classe não selada
public class Bulldog extends Dog {
}
```

### Exemplo 2: Uso em Hierarquias
```java
// Classe selada
public sealed class Shape permits Circle, Square {
}

// Classe não selada que herda da classe selada
public non-sealed class Circle extends Shape {
}

// Classe que estende a classe não selada
public class LargeCircle extends Circle {
}
```

## Explicação
Embora o uso de "non-sealed" ofereça mais liberdade na herança, é importante ter cuidado ao projetar suas hierarquias de classes. Um dos principais desafios é garantir que a lógica de sua aplicação não se torne confusa à medida que mais classes são adicionadas. 

### Armadilhas Comuns
- **Complexidade:** A utilização excessiva de "non-sealed" pode levar a hierarquias de classes complexas e difíceis de manter.
- **Incompatibilidade:** Tentar usar "non-sealed" em classes que não são seladas resultará em erros de compilação.
- **Planejamento:** É fundamental planejar a estrutura de classes com antecedência para evitar problemas futuros.

## Resumo em Uma Linha
O modificador "non-sealed" no Java permite que classes seladas sejam estendidas por subclasses não seladas, promovendo maior flexibilidade na herança.