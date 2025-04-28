<!--
Meta Description: # Synchronized em Java: Sincronização de Threads ## Sinopse O comando `synchronized` em Java é uma palavra-chave utilizada para controlar o acesso a m...
Meta Keywords: synchronized, uma, java, public, threads
-->

# Synchronized em Java: Sincronização de Threads

## Sinopse
O comando `synchronized` em Java é uma palavra-chave utilizada para controlar o acesso a métodos e blocos de código por múltiplas threads, garantindo que apenas uma thread possa executar o código sincronizado por vez, evitando condições de corrida e inconsistências nos dados.

## Documentação
A palavra-chave `synchronized` em Java serve para garantir que um método ou bloco de código seja acessado por apenas uma thread ao mesmo tempo. Isso é especialmente importante em aplicações multithreaded, onde múltiplas threads podem tentar modificar o mesmo recurso compartilhado simultaneamente.

### Propósito
O principal objetivo do `synchronized` é evitar que duas ou mais threads interfiram nas operações de um mesmo recurso simultaneamente, o que pode levar a resultados indesejados e comportamentos imprevisíveis.

### Uso
O `synchronized` pode ser aplicado de duas maneiras:
1. **Métodos sincronizados**: A palavra-chave é colocada antes da declaração do método. Isso bloqueia a instância do objeto (no caso de métodos de instância) ou a classe (no caso de métodos estáticos) enquanto o método está em execução.
   
   ```java
   public synchronized void metodoSincronizado() {
       // Lógica do método
   }
   ```

2. **Blocos sincronizados**: Permite uma granularidade maior, pois você pode sincronizar apenas partes específicas do código. Isso é feito utilizando um objeto como monitor.
   
   ```java
   public void metodo() {
       synchronized (this) {
           // Lógica do bloco sincronizado
       }
   }
   ```

## Exemplos
### Exemplo de Método Sincronizado
```java
public class Contador {
    private int contagem = 0;

    public synchronized void incrementar() {
        contagem++;
    }

    public synchronized int getContagem() {
        return contagem;
    }
}
```

### Exemplo de Bloco Sincronizado
```java
public class RecursoCompartilhado {
    private int recurso = 0;

    public void alterarRecurso() {
        synchronized (this) {
            recurso++;
        }
    }

    public int obterRecurso() {
        return recurso;
    }
}
```

## Explicação
Embora o `synchronized` seja uma ferramenta poderosa, seu uso inadequado pode levar a problemas como:
- **Deadlocks**: Quando duas ou mais threads estão esperando uma pela outra, impedindo a execução. Para evitar deadlocks, é importante ter uma estratégia clara de bloqueio.
- **Desempenho**: O uso excessivo de `synchronized` pode impactar negativamente o desempenho da aplicação, pois threads podem ficar bloqueadas, aguardando acesso ao recurso.
- **Granularidade de Bloqueio**: Sincronizar métodos inteiros pode ser desnecessário; utilizar blocos sincronizados ajuda a melhorar a eficiência, limitando o tempo de bloqueio.

## Resumo em Uma Linha
O `synchronized` em Java é utilizado para garantir a execução exclusiva de métodos ou blocos de código por uma única thread, prevenindo condições de corrida em ambientes multithreaded.