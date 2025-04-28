<!--
Meta Description: # "provides" em Java: Entendendo a Palavra-Chave para Serviços de Módulo ## Sinopse A palavra-chave `provides` em Java é utilizada no contexto do sist...
Meta Keywords: módulo, java, provides, que, serviço
-->

# "provides" em Java: Entendendo a Palavra-Chave para Serviços de Módulo

## Sinopse
A palavra-chave `provides` em Java é utilizada no contexto do sistema de módulos introduzido no Java 9, permitindo que um módulo declare quais serviços ele oferece para outros módulos.

## Documentação
A palavra-chave `provides` é parte da declaração de um módulo em Java, que se encontra no arquivo `module-info.java`. O propósito principal do `provides` é definir interfaces de serviço que um módulo implementa, permitindo que outros módulos dependam dessas implementações.

### Estrutura do Módulo
Um módulo é uma coleção de pacotes, que pode incluir classes e interfaces. Para definir um módulo, você deve criar um arquivo chamado `module-info.java` na raiz do seu módulo. A sintaxe básica para a declaração de `provides` é a seguinte:

```java
module nome.do.seu.modulo {
    provides NomeDaInterface with NomeDaClasseImplementadora;
}
```

### Propósito
O `provides` é usado para:
- Declarar serviços que o módulo oferece.
- Facilitar a implementação de padrões de design como o Service Provider Interface (SPI).
- Melhorar a modularidade e a encapsulação em aplicações Java.

## Exemplos
Aqui estão alguns exemplos práticos do uso do `provides`:

### Exemplo 1: Implementação Simples
```java
// Arquivo: module-info.java
module meu.modulo {
    provides com.exemplo.Servico with com.exemplo.impl.ServicoImpl;
}

// Interface de Serviço
package com.exemplo;

public interface Servico {
    void executar();
}

// Implementação do Serviço
package com.exemplo.impl;

import com.exemplo.Servico;

public class ServicoImpl implements Servico {
    @Override
    public void executar() {
        System.out.println("Serviço Executado!");
    }
}
```

### Exemplo 2: Uso de Módulos
```java
// Arquivo: module-info.java
module consumidor.modulo {
    requires meu.modulo;
}
```

No módulo consumidor, você pode usar a implementação do serviço fornecido pelo módulo `meu.modulo`.

## Explicação
Alguns pontos a considerar ao usar `provides`:

- **Múltiplas Implementações**: Você pode declarar várias implementações para a mesma interface de serviço usando várias instruções `provides`.
- **Declarações em Módulos Diferentes**: Certifique-se de que os módulos que consomem o serviço estão corretamente configurados para requerer o módulo que fornece o serviço.
- **Erros Comuns**: Um erro comum é esquecer de adicionar a dependência no módulo que consome o serviço, resultando em `ClassNotFoundException`.

## Resumo em Uma Linha
A palavra-chave `provides` em Java declara quais serviços um módulo oferece, facilitando a implementação e a utilização de interfaces de serviço em um sistema modular.