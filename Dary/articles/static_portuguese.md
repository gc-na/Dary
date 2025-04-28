<!--
Meta Description: # O Que é "static" em Java: Entenda sua Importância e Utilização ## Sinopse O modificador "static" em Java é utilizado para declarar membros de classe...
Meta Keywords: static, classe, que, não, contador
-->

# O Que é "static" em Java: Entenda sua Importância e Utilização

## Sinopse
O modificador "static" em Java é utilizado para declarar membros de classe que pertencem à classe em si, e não a instâncias individuais da classe. Isso permite que variáveis e métodos sejam acessíveis sem a necessidade de criar um objeto da classe.

## Documentação
O modificador "static" desempenha um papel crucial em Java, especialmente no gerenciamento de memória e na estruturação do código. Quando um membro (variável ou método) é declarado como "static", ele se torna um membro da classe, o que significa que:

- **Variáveis Static**: Uma variável estática é compartilhada entre todas as instâncias da classe. Isso é útil quando você deseja contar o número de objetos criados ou manter uma configuração que todas as instâncias devem compartilhar.
  
- **Métodos Static**: Métodos estáticos podem ser chamados sem a necessidade de instanciar a classe. Eles são frequentemente utilizados para criar funções utilitárias que não dependem do estado de um objeto.

### Exemplo de Declaração
```java
public class ExemploStatic {
    static int contador = 0;

    public ExemploStatic() {
        contador++; // Incrementa o contador sempre que uma nova instância é criada
    }

    static void mostrarContador() {
        System.out.println("Contador de instâncias: " + contador);
    }
}
```

## Exemplos
### Exemplo 1: Usando Variáveis Static
```java
public class Contador {
    static int totalInstancias = 0;

    public Contador() {
        totalInstancias++;
    }

    static void mostrarTotal() {
        System.out.println("Total de instâncias: " + totalInstancias);
    }

    public static void main(String[] args) {
        new Contador();
        new Contador();
        Contador.mostrarTotal(); // Saída: Total de instâncias: 2
    }
}
```

### Exemplo 2: Usando Métodos Static
```java
public class Util {
    static int somar(int a, int b) {
        return a + b;
    }

    public static void main(String[] args) {
        int resultado = Util.somar(5, 10);
        System.out.println("Resultado da soma: " + resultado); // Saída: Resultado da soma: 15
    }
}
```

## Explicação
### Armadilhas Comuns
1. **Uso de Membros Não Estáticos**: Um método estático não pode acessar diretamente variáveis de instância (não estáticas) ou métodos não estáticos da classe, a menos que crie uma instância da classe.
   
2. **Inicialização de Variáveis Estáticas**: Variáveis estáticas são inicializadas apenas uma vez, quando a classe é carregada. Isso pode levar a comportamentos inesperados se não for bem compreendido.

3. **Múltiplas Instâncias**: Alterar uma variável estática afeta todas as instâncias da classe, o que pode causar confusão se não for tratado adequadamente.

4. **Não Substituição**: Métodos estáticos não podem ser sobrescritos (overridden) em subclasses, embora possam ser ocultados (hidden).

## Resumo em Uma Linha
O modificador "static" em Java permite declarar membros de classe que podem ser acessados sem instanciar a classe, facilitando a gestão de variáveis e métodos compartilhados.