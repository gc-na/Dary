<!--
Meta Description: # Throws em Java: Entenda como Lidar com Exceções ## Sinopse O comando `throws` em Java é utilizado para declarar que um método pode lançar uma ou mai...
Meta Keywords: exceções, throws, que, método, para
-->

# Throws em Java: Entenda como Lidar com Exceções

## Sinopse
O comando `throws` em Java é utilizado para declarar que um método pode lançar uma ou mais exceções. Essa palavra-chave é fundamental para o tratamento de exceções, permitindo que o programador informe ao compilador e aos usuários do método quais exceções podem ser lançadas e que devem ser tratadas.

## Documentação
### Propósito
O `throws` é utilizado na assinatura de um método para indicar que ele pode lançar exceções que não são tratadas dentro de seu corpo. Isso é especialmente importante para exceções verificadas (checked exceptions), que obrigam o desenvolvedor a tratar ou declarar a exceção.

### Uso
A sintaxe do `throws` é a seguinte:
```java
public void nomeDoMetodo() throws NomeDaExcecao {
    // corpo do método
}
```
Quando um método que utiliza `throws` é chamado, o código que chama esse método deve estar preparado para lidar com a exceção, seja através de um bloco `try-catch` ou por meio da declaração de `throws` na assinatura do próprio método.

### Detalhes
- **Exceções Não Verificadas:** O `throws` não é necessário para exceções não verificadas (unchecked exceptions), como `NullPointerException` ou `ArrayIndexOutOfBoundsException`, pois estas podem ser tratadas a qualquer momento.
- **Múltiplas Exceções:** É possível declarar várias exceções separadas por vírgula:
```java
public void meuMetodo() throws IOException, SQLException {
    // corpo do método
}
```
- **Propagação de Exceções:** O uso do `throws` permite a propagação de exceções, facilitando o design de APIs e o tratamento de erros em um nível mais elevado.

## Exemplos
### Exemplo Básico
```java
public class ExemploThrows {
    public static void main(String[] args) {
        try {
            metodoQueLancaExcecao();
        } catch (Exception e) {
            System.out.println("Exceção capturada: " + e.getMessage());
        }
    }

    public static void metodoQueLancaExcecao() throws Exception {
        throw new Exception("Esta é uma exceção lançada.");
    }
}
```

### Exemplo com Múltiplas Exceções
```java
public class ExemploMultiplasExcecoes {
    public static void main(String[] args) {
        try {
            metodoQueLancaMultiplasExcecoes();
        } catch (IOException | SQLException e) {
            System.out.println("Exceção capturada: " + e.getMessage());
        }
    }

    public static void metodoQueLancaMultiplasExcecoes() throws IOException, SQLException {
        // Lógica que pode lançar IOException ou SQLException
    }
}
```

## Explicação
Ao utilizar `throws`, os desenvolvedores devem estar cientes de alguns pontos importantes:
- **Tratamento de Exceções:** Sempre que um método que declara `throws` é invocado, deve-se lidar com as exceções lançadas para evitar erros em tempo de execução.
- **Documentação:** É uma boa prática documentar as exceções que um método pode lançar, utilizando comentários Javadoc, para que outros desenvolvedores possam entender facilmente o comportamento do método.
- **Propagação de Exceções:** Enquanto a propagação de exceções pode ser útil, o uso excessivo de `throws` pode tornar o código difícil de seguir. Avalie se as exceções devem ser tratadas localmente ou se devem ser propagadas.

## Resumo em Uma Linha
O `throws` em Java é uma declaração que permite que métodos informem quais exceções podem ser lançadas, garantindo um tratamento adequado de erros.