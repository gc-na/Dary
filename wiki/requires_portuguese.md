<!--
Meta Description: # A Importância da Palavra-chave "requires" no Java ## Sinopse A palavra-chave `requires` é um elemento fundamental no sistema de módulos introduzido ...
Meta Keywords: modulo, requires, java, que, dependências
-->

# A Importância da Palavra-chave "requires" no Java

## Sinopse
A palavra-chave `requires` é um elemento fundamental no sistema de módulos introduzido no Java 9, que permite definir dependências entre módulos, promovendo um design mais modular e organizado de aplicações Java.

## Documentação
A palavra-chave `requires` é utilizada na declaração de um módulo no arquivo `module-info.java`, que é responsável por descrever as características de um módulo Java. A sua principal função é especificar quais módulos são necessários para que o módulo atual funcione corretamente. Isso facilita o gerenciamento de dependências e a encapsulação do código.

### Propósito
O uso do `requires` ajuda a evitar conflitos de dependências e garante que o código só acesse os módulos que explicitamente declara como dependências. Isso promove uma arquitetura mais limpa e compreensível.

### Uso
A sintaxe básica para declarar um módulo que requer outro módulo é a seguinte:
```java
module nome.do.seu.modulo {
    requires nome.do.modulo.requerido;
}
```
Você pode também indicar a versão do módulo requerido, usando a seguinte sintaxe:
```java
module nome.do.seu.modulo {
    requires nome.do.modulo.requerido versão;
}
```

## Exemplos
Aqui estão alguns exemplos para ilustrar o uso da palavra-chave `requires`:

### Exemplo 1: Dependência Simples
```java
module meu.modulo {
    requires java.sql;
}
```
Neste exemplo, o módulo `meu.modulo` depende do módulo `java.sql`, permitindo o uso de funcionalidades relacionadas a bancos de dados.

### Exemplo 2: Dependência com Versão
```java
module meu.modulo {
    requires transitive outro.modulo;
    requires outro.modulo versão 1.0.0;
}
```
Aqui, `meu.modulo` exige que `outro.modulo` esteja na versão 1.0.0 e, além disso, a palavra-chave `transitive` permite que outros módulos que dependem de `meu.modulo` também tenham acesso a `outro.modulo`.

## Explicação
Embora a palavra-chave `requires` seja bastante útil, existem algumas considerações a serem observadas:
- **Omissão de Dependências**: Se um módulo não declarar corretamente suas dependências, pode resultar em `ClassNotFoundException` em tempo de execução, já que as classes requeridas não estarão disponíveis.
- **Ciclo de Dependências**: Dependências circulares entre módulos podem causar problemas de compilação e devem ser evitadas.
- **Versões**: Especificar versões é importante, mas pode ser desafiador, especialmente em projetos grandes onde as dependências podem mudar frequentemente.

## Resumo em Uma Frase
A palavra-chave `requires` em Java é essencial para declarar dependências entre módulos, promovendo um design modular e organizado das aplicações.