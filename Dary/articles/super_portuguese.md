<!--
Meta Description: # O Uso da Palavra-Chave "super" em JAVA: Entenda Seu Funcionamento ## Sinopse A palavra-chave "super" em Java é um recurso essencial que permite aces...
Meta Keywords: super, superclasse, animal, palavra, chave
-->

# O Uso da Palavra-Chave "super" em JAVA: Entenda Seu Funcionamento

## Sinopse
A palavra-chave "super" em Java é um recurso essencial que permite acessar métodos e variáveis da superclasse, facilitando a herança e a reutilização de código.

## Documentação
A palavra-chave **super** é utilizada em Java para referenciar membros (variáveis e métodos) da superclasse de uma classe. Isso é especialmente útil em cenários de herança, onde uma subclasse pode precisar acessar ou modificar o comportamento herdado da superclasse.

### Propósito
O principal propósito da palavra-chave "super" é permitir que a subclasse interaja com os membros da sua superclasse, garantindo que o código mantenha a hierarquia de classes organizada e eficiente.

### Uso
Existem duas utilizações principais da palavra-chave "super":

1. **Acesso a Variáveis**: Quando uma subclasse possui uma variável com o mesmo nome que uma da superclasse, a palavra-chave "super" é usada para referenciar a variável da superclasse.
   
   ```java
   class Animal {
       String tipo = "Animal";
   }

   class Cachorro extends Animal {
       String tipo = "Cachorro";
       
       void mostrarTipo() {
           System.out.println(super.tipo); // Exibe "Animal"
       }
   }
   ```

2. **Chamada de Métodos**: Similar ao acesso a variáveis, "super" pode ser usado para chamar um método da superclasse que foi sobrescrito na subclasse.
   
   ```java
   class Animal {
       void fazerSom() {
           System.out.println("Som de Animal");
       }
   }

   class Cachorro extends Animal {
       void fazerSom() {
           super.fazerSom(); // Chama o método da superclasse
           System.out.println("Au Au");
       }
   }
   ```

3. **Chamada de Construtores**: A palavra-chave "super" também é utilizada para chamar o construtor da superclasse. Isso é feito na primeira linha do construtor da subclasse.
   
   ```java
   class Animal {
       Animal() {
           System.out.println("Construtor de Animal");
       }
   }

   class Cachorro extends Animal {
       Cachorro() {
           super(); // Chama o construtor da superclasse
           System.out.println("Construtor de Cachorro");
       }
   }
   ```

## Exemplos
Aqui estão exemplos adicionais que demonstram o uso de "super":

```java
class Veiculo {
    int velocidade = 60;

    void acelerar() {
        System.out.println("Acelerando...");
    }
}

class Carro extends Veiculo {
    int velocidade = 120;

    void mostrarVelocidade() {
        System.out.println("Velocidade do veículo: " + super.velocidade); // Exibe "60"
    }

    void acelerar() {
        super.acelerar(); // Chama método da superclasse
        System.out.println("Acelerando o carro...");
    }
}
```

## Explicação
Embora a palavra-chave "super" seja poderosa, é importante estar atento a alguns detalhes:

- **Sombreamento de Variáveis**: Quando uma subclasse define uma variável com o mesmo nome de uma variável da superclasse, a variável da subclasse "sombra" a da superclasse. O uso de "super" é necessário para acessar a variável original da superclasse.
  
- **Métodos Sobrescritos**: Se um método é sobrescrito na subclasse, é possível chamar a versão da superclasse usando "super". Isso é útil para estender a funcionalidade de um método existente.

- **Primeira Linha em Construtores**: A chamada "super()" deve estar sempre na primeira linha do construtor da subclasse, caso contrário, ocorrerá um erro de compilação.

## Resumo em Uma Frase
A palavra-chave "super" em Java é utilizada para acessar membros da superclasse, facilitando a herança e a reutilização de código nas subclasses.