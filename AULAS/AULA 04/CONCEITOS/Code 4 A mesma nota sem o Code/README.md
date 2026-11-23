# Code 4 · A mesma nota sem o nó Code

O par do exemplo **Code 3**. Serve para comparar quantos nós o Code economiza. Roda sem credencial nenhuma.

## O que faz

Os mesmos cinco pedidos da Orbita recebem a mesma nota, agora sem o nó Code. Cada critério vira um Switch ou um IF. Cada pontuação vira um Edit Fields com valor fixo. No fim, o **Somar a nota** junta os pontos e o Switch **Qual faixa?** separa em quente, morno e frio. São **25 nós** para fazer o que o **Nota do lead** faz sozinho.

| Pedido | Nota | Faixa |
|---|---|---|
| Marina Souza | 95 | quente |
| Pedro Lima | 55 | morno |
| Ana Paula Reis | 70 | quente |
| Rafa | 10 | frio |
| Lia, só com nome | 0 | frio |

## Como testar

Clique em **Execute workflow**. Abra o **Somar a nota** e os três nós do fim. As notas são as mesmas do Code: 95, 55, 70, 10 e 0. Cada pedido chega por um caminho, então o mesmo nó roda mais de uma vez. Use o seletor **Run 1 of N**, no alto da saída, para ver todos.

## O que treinar

1. Siga a Marina pelo canvas. Por quais nós ela passa até virar quente?
2. A Orbita decide que o prazo "este mês" passa a valer 50. Mude aqui e depois no exemplo **Code 3**. Em qual foi mais rápido?
3. Imagine um critério novo, a área do cliente, com cinco opções. Quantos nós entram aqui? E quantas linhas entram no Code?

## Erros comuns

Em cada Edit Fields, **Include Other Input Fields** fica ligado. Desligado, o pedido perde os outros campos.

No **Qual faixa?**, a ordem das regras conta. A regra de 70 vem antes da regra de 40.

O Switch compara o texto exato. Um prazo escrito de outro jeito cai na saída **Fallback** e vale 0.
