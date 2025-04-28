<!--
Meta Description: # Comando "continue" em Java: Como Funciona e Quando Usar ## Sinopse O comando `continue` em Java é utilizado para interromper a iteração atual de um ...
Meta Keywords: continue, iteração, java, para, laço
-->

# Comando "continue" em Java: Como Funciona e Quando Usar

## Sinopse
O comando `continue` em Java é utilizado para interromper a iteração atual de um laço (loop) e passar para a próxima iteração, facilitando o controle do fluxo de execução em loops como `for`, `while` e `do-while`.

## Documentação
O `continue` é uma instrução de controle de fluxo que permite que o programa salte a parte restante de um laço e inicie a próxima iteração. Isso é útil quando se deseja pular a execução de certas condições dentro do laço, sem sair completamente dele.

### Uso
O comando `continue` pode ser utilizado em qualquer laço de repetição em Java. Sua sintaxe básica é a seguinte:

```java
continue; // Para loops sem condição
```

No caso de um loop com uma condição, como um `for` ou `while`, o `continue` pode ser utilizado junto a uma instrução condicional para determinar quando pular a iteração.

### Exemplo de Sintaxe
```java
for (int i = 0; i < 10; i++) {
    if (i % 2 == 0) {
        continue; // Pula a iteração se i for par
    }
    System.out.println(i); // Imprime apenas números ímpares
}
```

## Exemplos
### Exemplo 1: Usando `continue` em um Loop `for`
```java
for (int i = 0; i < 10; i++) {
    if (i == 5) {
        continue; // Pula a iteração quando i é igual a 5
    }
    System.out.println(i);
}
// Saída: 0, 1, 2, 3, 4, 6, 7, 8, 9
```

### Exemplo 2: Usando `continue` em um Loop `while`
```java
int i = 0;
while (i < 10) {
    i++;
    if (i % 2 == 0) {
        continue; // Pula os números pares
    }
    System.out.println(i);
}
// Saída: 1, 3, 5, 7, 9
```

## Explicação
Uma armadilha comum ao usar o `continue` é esquecer que ele apenas pula para a próxima iteração do laço, não para o final do laço. Isso pode levar a loops que não terminam como esperado, especialmente se o controle da variável de loop não for bem gerenciado. Além disso, o uso excessivo de `continue` pode tornar o código menos legível. Para manter a clareza, é recomendável usar `continue` com cautela e nos contextos apropriados.

## Resumo em Uma Linha
O comando `continue` em Java permite pular a execução da iteração atual de um laço, iniciando imediatamente a próxima iteração, facilitando o controle do fluxo em loops.