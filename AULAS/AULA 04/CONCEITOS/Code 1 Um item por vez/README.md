# Code 1 · Um item por vez

Primeiro contato com o nó Code, antes do captador da Orbita. Roda sem credencial nenhuma.

## O que faz

Três pedidos fictícios de uma papelaria passam pelo nó **Calcular total**. O código multiplica a quantidade pelo preço, decide o frete e soma o total. Compra a partir de R$ 200 não paga frete. Abaixo disso, o frete é R$ 25.

| Cliente | Quantidade × preço | Subtotal | Frete | Total |
|---|---|---|---|---|
| Bruna | 3 × 80 | 240 | 0 | 240 |
| Caio | 2 × 45 | 90 | 25 | 115 |
| Dani | 10 × 20 | 200 | 0 | 200 |

## Como testar

Clique em **Execute workflow** e abra o **Calcular total**. Entram 3 itens e saem 3 itens. Cada um ganhou `subtotal`, `frete` e `total`. Confira os totais 240, 115 e 200.

## O que treinar

1. Antes de rodar, calcule no papel o total do Caio.
2. No código, faça o frete grátis começar em 250. O pedido da Bruna, de 240, passa a pagar frete.
3. Crie o campo `desconto`, com 10% do subtotal, e devolva ele junto com os outros.

## Erros comuns

O modo do nó precisa ser **Run Once for Each Item**. Nesse modo, `$json` é o item da vez.

Devolva sempre `{ json: { ... } }`. É o formato de item que os outros nós esperam.

Número que chega como texto engana na soma: `"3" + 2` vira `"32"`. Converta antes com `Number(...)`.
