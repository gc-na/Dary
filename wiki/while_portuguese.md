<!--
Meta Description: # Estrutura de Controle "while" em Java: Como Usar e Exemplos Práticos ## Sinopse O comando "while" em Java é uma estrutura de controle que permite a ...
Meta Keywords: condição, while, número, java, uma
-->

# Estrutura de Controle "while" em Java: Como Usar e Exemplos Práticos

## Sinopse
O comando "while" em Java é uma estrutura de controle que permite a execução repetida de um bloco de código enquanto uma determinada condição for verdadeira. Essa funcionalidade é fundamental para a criação de loops em programas Java, possibilitando a execução contínua de instruções até que uma condição de parada seja atendida.

## Documentação
### Propósito
A estrutura "while" é utilizada quando se deseja repetir um bloco de código indeterminadamente, até que uma condição específica não seja mais satisfeita. É útil em situações em que não se sabe de antemão quantas iterações serão necessárias, permitindo uma flexibilidade maior na execução de lógicas complexas.

### Sintaxe
A sintaxe básica do comando "while" em Java é a seguinte:

```java
while (condição) {
    // bloco de código a ser executado
}
```

### Uso
1. **Condição:** A expressão booleana que será avaliada antes da execução do bloco de código. Se for verdadeira, o bloco será executado; se for falsa, o loop será encerrado.
2. **Bloco de Código:** O conjunto de instruções a serem repetidas enquanto a condição for verdadeira.

### Detalhes
- O bloco de código dentro do loop "while" pode conter qualquer tipo de instrução válida em Java, incluindo outras estruturas de controle.
- É fundamental garantir que a condição eventualmente se torne falsa para evitar loops infinitos, que podem travar a aplicação.

## Exemplos

### Exemplo Básico
```java
int i = 0;
while (i < 5) {
    System.out.println("Valor de i: " + i);
    i++;
}
```
*Saída:*
```
Valor de i: 0
Valor de i: 1
Valor de i: 2
Valor de i: 3
Valor de i: 4
```

### Exemplo com Condição de Parada
```java
int numero = 1;
while (numero <= 10) {
    System.out.println("Número: " + numero);
    numero++;
}
```
*Saída:*
```
Número: 1
Número: 2
Número: 3
Número: 4
Número: 5
Número: 6
Número: 7
Número: 8
Número: 9
Número: 10
```

## Explicação
### Armadilhas Comuns
- **Loops Infinitos:** Um erro comum é não atualizar a condição dentro do loop, resultando em uma execução infinita. Sempre verifique se a variável de controle está sendo alterada corretamente.
  
- **Condição Sempre Verdadeira:** Se a condição for mal formulada, você pode acabar criando um loop interminável. Por exemplo, `while (true)` sem uma instrução de saída pode travar o programa.

### Notas Adicionais
- O uso de `break` pode ser implementado para sair de um loop antes que a condição se torne falsa.
- A estrutura "while" é frequentemente utilizada em situações onde a condição depende de entradas do usuário ou de outras operações que não podem ser previstas antes da execução.

## Resumo em Uma Linha
O comando "while" em Java permite a repetição de um bloco de código enquanto uma condição booleana for verdadeira, sendo essencial para a criação de loops dinâmicos em programas.