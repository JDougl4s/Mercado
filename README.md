[README.md](https://github.com/user-attachments/files/29297092/README.md)
# 🛒 Totem Mercado

Sistema de autoatendimento desenvolvido em **Java** para praticar conceitos de **Programação Orientada a Objetos (POO)**.

O projeto simula o funcionamento de um totem de mercado, permitindo criar pedidos, listar produtos, adicionar itens, calcular o valor total, aplicar descontos, finalizar pedidos e gerar um ticket.

---

## 📌 Objetivo do projeto

Este projeto foi criado com fins de estudo para aplicar, na prática, conceitos como:

- Classes e objetos
- Encapsulamento
- Herança
- Classes abstratas
- Interfaces
- Polimorfismo
- Enumerações
- Associação e composição
- Coleções com `List`
- Estruturas de repetição
- Menus com `Scanner`
- Organização em pacotes

---

## ⚙️ Funcionalidades

- Criar um novo pedido
- Listar os produtos disponíveis
- Buscar produtos pelo ID
- Adicionar produtos ao pedido
- Informar a quantidade de cada produto
- Calcular o subtotal dos itens
- Calcular o total do pedido
- Aplicar desconto fixo
- Aplicar desconto percentual
- Finalizar o pedido
- Consultar o status do pedido
- Gerar e imprimir um ticket
- Criar novos pedidos pelo menu principal

---

## 🧱 Estrutura do projeto

```text
src/main/java/
└── br/com/projetomercado/
    ├── app/
    │   └── MercadoApp.java
    │
    ├── dominio/
    │   ├── Produto.java
    │   ├── Alimento.java
    │   ├── Bebida.java
    │   ├── Limpeza.java
    │   ├── CatalogoProdutos.java
    │   ├── ItemPedido.java
    │   ├── Pedido.java
    │   ├── StatusPedido.java
    │   └── Ticket.java
    │
    ├── interfaces/
    │   └── Desconto.java
    │
    └── servico/
        ├── DescontoFixo.java
        └── DescontoPercentual.java
```

---

## 🧠 Conceitos de POO aplicados

### Classe abstrata

A classe `Produto` representa as características comuns entre todos os produtos.

```java
public abstract class Produto {
    private int id;
    private String nome;
    private double preco;

    public abstract String getTipo();
    public abstract String getDescricao();
}
```

Ela não pode ser instanciada diretamente. Suas subclasses concretas são:

- `Alimento`
- `Bebida`
- `Limpeza`

### Herança

As classes específicas herdam os atributos e comportamentos de `Produto`.

```java
public class Alimento extends Produto {
}
```

### Interface

A interface `Desconto` define um contrato para diferentes estratégias de desconto.

```java
public interface Desconto {
    double aplicarDesconto(double valorOriginal);
}
```

### Polimorfismo

O pedido trabalha com a interface `Desconto`, sem precisar saber qual implementação concreta está sendo utilizada.

```java
private Desconto estrategiaDesconto;
```

Assim, o pedido pode receber:

```java
new DescontoFixo(10);
```

ou:

```java
new DescontoPercentual(15);
```

### Enumeração

O `enum StatusPedido` representa os possíveis estados de um pedido.

```java
public enum StatusPedido {
    CRIANDO,
    AGUARDANDO_PAGAMENTO,
    PAGO,
    EM_PREPARO,
    RETIRADO
}
```

---

## 🔄 Fluxo principal

```text
Iniciar o sistema
        ↓
Criar um novo pedido
        ↓
Listar produtos
        ↓
Selecionar produto e quantidade
        ↓
Adicionar ItemPedido
        ↓
Calcular total
        ↓
Aplicar desconto, se necessário
        ↓
Finalizar pedido
        ↓
Gerar ticket
```

---

## 🛠️ Tecnologias utilizadas

- Java 17
- Apache NetBeans
- Maven
- Programação Orientada a Objetos
- Git e GitHub

---

## ▶️ Como executar no NetBeans

1. Faça o clone do repositório:

```bash
git clone https://github.com/jdougl4s/totem-mercado.git
```

2. Abra o Apache NetBeans.

3. Acesse:

```text
File > Open Project
```

4. Selecione a pasta do projeto.

5. Execute a classe principal:

```text
br.com.projetomercado.app.MercadoApp
```

---

## 💻 Exemplo do menu

```text
===== TOTEM MERCADO =====
1 - Criar novo pedido
0 - Sair
```

Após criar um pedido:

```text
===== PEDIDO PED-001 =====
1 - Listar produtos
2 - Adicionar produto
3 - Mostrar total
4 - Aplicar desconto fixo
5 - Aplicar desconto percentual
6 - Finalizar pedido
7 - Mostrar status
8 - Gerar ticket
9 - Voltar ao menu principal
```

---

## 🚧 Melhorias futuras

- Adicionar formas de pagamento
- Implementar todos os status do pedido
- Criar histórico de pedidos
- Persistir os dados em banco de dados
- Validar descontos inválidos
- Impedir valores negativos
- Exibir os itens no ticket
- Criar testes automatizados com JUnit
- Desenvolver uma interface gráfica
- Integrar o projeto com uma API

---

## 👨‍💻 Autor

Desenvolvido por **Douglas**.

GitHub: [@jdougl4s](https://github.com/jdougl4s)

---

## 📄 Licença

Este projeto foi desenvolvido para fins educacionais.
