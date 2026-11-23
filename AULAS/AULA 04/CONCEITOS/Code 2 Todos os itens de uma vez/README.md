# Code 2 · Todos os itens de uma vez

O outro modo do nó Code. Roda sem credencial nenhuma.

## O que faz

Cinco vendas fictícias de um dia entram no nó **Resumir vendas**. O código olha todas de uma vez e devolve um item só, com a quantidade de vendas, o total, a média e a maior venda.

| Vendedor | Valor |
|---|---|
| Ana | 120 |
| Beto | 80 |
| Ana | 300 |
| Carla | 50 |
| Beto | 250 |

Resultado esperado: 5 vendas, total 800, média 160, maior venda 300, da Ana.

## Como testar

Clique em **Execute workflow** e abra o **Resumir vendas**. Entram 5 itens e sai 1. Confira total 800, média 160 e maior venda 300, da Ana.

## O que treinar

1. No **Gatilho Manual**, mude a venda da Carla para 500 e rode de novo. De quem é a maior venda agora?
2. Acrescente ao resultado o campo `menor_venda`.
3. Compare com o exemplo **Code 1**. Lá entram 3 itens e saem 3. Aqui entram 5 e sai 1.

## Erros comuns

Neste modo o retorno é uma lista, `[ { json: { ... } } ]`. Repare nos colchetes.

`$json` mostra um item só. Para ver todos, use `$input.all()`.

Se não chegar nenhuma venda, `vendas[0]` não existe e o código para. Num fluxo de verdade, trate a lista vazia antes.
