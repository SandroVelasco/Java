- [JUnit](#junit)
- [TDD](#test-driven-development--tdd-)

# JUnit
Biblioteca para desenvolvimento de testes.

O fluxo da criação de testes com o JUnit consiste em:

- Classe que será testada.
- Classe de teste.

## Classe que será testada
```java
public class Calculadora {
    public double soma(double n1, double n2) {
        return n1 + n2;
    }
}
```
## Classe de teste
```java
import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.*;

public class CalculadoraTest {

    @Test
    public void somaComDoisNumerosPositivos() {
        Calculadora calculadora = new Calculadora();
        double resultado = calculadora.soma(1, 2);

        assertEquals(3, resultado);
    }
}
```

# Test Driven Development (TDD)
Representa um modelo para a utilização de testes. O modelo consiste em um workflow de:

`Criação do teste` -> `Implementação das funcionalidades` -> `Refatoração de código` 

Para entender mais, pesquise por exemplos na internet.