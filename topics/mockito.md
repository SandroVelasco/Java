- [Mockito](#mockito)
- [Exemplo](#exemplo)
- [Formas de iniciar um mock](#formas-de-iniciar-um-mock)
- [Ações](#acões)
    - [Mockito.when](#when)
    - [Mockito.verify](#verify)

# Mockito
Serve para isolar determinados comportamentos de uma classe, como, por exemplo, pesquisas em banco de dados.

Um mock é uma réplica de uma classe.

# Exemplo
```Java
@Test
public void HelloWorldMockito() {
    LeilaoDao mock = Mockito.mock(LeilaoDao.class);
    List<Leilao> leilaos = mock.buscarTodos();
    assertTrue(leilaos.isEmpty());
}
```

# Formas de iniciar um mock
**1. Direto no método**
```Java
<nome_da_classe> <nome_da_variavel> = Mockito.mock(<nome_da_classe>.class);
```

**2. Separado do método [PREFERIDO PARA VÁRIOS MÉTODOS]**
```java
// Como atributo da classe
@Mock
public <nome_da_classe> <nome_da_variavel>;

@BeforeEach
public void beforeEach() {
    // Todos os atributos marcados com a anotação @Mock serão inicializados.
    MockitoAnnotations.initMocks(this);
}
```

# Ações
## When
Quando (when) algo acontecer, tome uma decisão.

```java
Mockito.when()
.thenReturn()   // 1
.thenThrow()    // 2
```

## Verify
Verifique se um método foi chamado.
```java
Mockito.verify(<objeto>).salvar(leilao);
Mockito.verify(leilaoDao).salvar(leilao);
```