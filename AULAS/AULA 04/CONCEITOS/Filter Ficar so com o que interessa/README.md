# Filter · Ficar só com o que interessa

O nó Filter ao lado de um IF com a mesma pergunta. Roda sem credencial nenhuma.

## O que faz

Seis pedidos fictícios de uma loja. O Filter **Pagos a partir de 100** deixa passar só quem cumpre as duas condições: status `pago` e valor de 100 ou mais. Embaixo, o IF **Pago a partir de 100?** faz a mesma pergunta. O IF tem duas saídas. O Filter tem uma, e o que não passa para ali.

| Cliente | Valor | Status | Passa? |
|---|---|---|---|
| Bia | 250 | pago | sim |
| Léo | 80 | pago | não |
| Nina | 400 | pendente | não |
| Otto | 120 | pago | sim |
| Rute | 100 | pago | sim |
| Saulo | 60 | cancelado | não |

## Como testar

Clique em **Execute workflow**. No caminho de cima, 3 pedidos chegam em **Seguem para a entrega**: Bia, Otto e Rute. No caminho de baixo, 3 saem pelo true e 3 pelo false.

## O que treinar

1. Antes de rodar, conte quantos pedidos passam.
2. No Filter, troque **AND** por **OR** e rode. Agora passa quem pagou ou quem comprou 100 ou mais. Só o Saulo fica de fora.
3. Abra o Filter depois de rodar. Na saída, a aba **Discarded** guarda os pedidos que não passaram.

## Erros comuns

Se o pedido que não passou também precisa de um destino, o nó certo é o IF.

Com **AND**, todas as condições têm de ser verdadeiras. Com **OR**, basta uma.

`Pago` com letra maiúscula não é igual a `pago`. Ligue **Ignore Case** ou padronize o texto antes.
