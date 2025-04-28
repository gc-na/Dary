<!--
Meta Description: # Comando "if" em Java: Estruturas de Controle de Fluxo ## Sinopse O comando "if" em Java é uma estrutura de controle que permite a execução condicion...
Meta Keywords: código, bloco, java, uma, else
-->

# Comando "if" em Java: Estruturas de Controle de Fluxo

## Sinopse
O comando "if" em Java é uma estrutura de controle que permite a execução condicional de blocos de código, com base na avaliação de expressões booleanas. É uma das formas mais fundamentais de controle de fluxo, permitindo que programas tomem decisões em tempo de execução.

## Documentação
### Propósito
O comando "if" é utilizado para avaliar uma condição e executar um bloco de código apenas se essa condição for verdadeira. Caso contrário, o código dentro do bloco "if" é ignorado. Essa estrutura é essencial para a criação de lógicas complexas em programas Java.

### Uso
A sintaxe básica do comando "if" é a seguinte:

```java
if (condição) {
    // bloco de código a ser executado se a condição for verdadeira
}
```

É possível incluir uma cláusula "else" para definir um bloco de código que será executado quando a condição for falsa:

```java
if (condição) {
    // bloco de código se a condição for verdadeira
} else {
    // bloco de código se a condição for falsa
}
```

Além disso, pode-se usar "else if" para testar múltiplas condições:

```java
if (condição1) {
    // bloco de código se condição1 for verdadeira
} else if (condição2) {
    // bloco de código se condição2 for verdadeira
} else {
    // bloco de código se nenhuma das condições anteriores for verdadeira
}
```

### Detalhes
- **Condições**: As condições devem sempre resultar em um valor booleano (`true` ou `false`). Isso pode ser feito através de operadores de comparação, como `>`, `<`, `==`, `!=`, etc.
- **Bloco de código**: O bloco de código pode conter uma ou mais instruções. Se houver apenas uma instrução, as chaves `{}` podem ser omitidas.
- **Aninhamento**: Estruturas "if" podem ser aninhadas, ou seja, um bloco "if" pode conter outro bloco "if" dentro dele, permitindo uma maior complexidade nas condições.

## Exemplos
### Exemplo Básico
```java
int numero = 10;

if (numero > 5) {
    System.out.println("O número é maior que 5");
} else {
    System.out.println("O número é 5 ou menor");
}
```

### Exemplo com "else if"
```java
int nota = 85;

if (nota >= 90) {
    System.out.println("Aprovado com Distinção");
} else if (nota >= 75) {
    System.out.println("Aprovado");
} else {
    System.out.println("Reprovado");
}
```

## Explicação
### Armadilhas Comuns
1. **Erro de Sintaxe**: Negligenciar as chaves ao escrever um bloco de código pode levar a erros de lógica. Sempre que houver múltiplas instruções, use chaves `{}`.
2. **Ambiguidade**: Cuidado ao usar operadores de comparação. Confundir `==` (igualdade) com `=` (atribuição) pode causar erros de lógica.
3. **Condições complexas**: Ao combinar várias condições usando `&&` (E) e `||` (OU), verifique a lógica para garantir que as expressões sejam avaliadas corretamente.

### Notas Adicionais
- O comando "if" é a base para outras estruturas de controle como "switch", "while" e "for".
- O uso de "if" é fundamental para a implementação de algoritmos que exigem decisões baseadas em condições variáveis.

## Resumo em Uma Linha
O comando "if" em Java é uma estrutura de controle que permite a execução condicional de blocos de código com base em expressões booleanas.