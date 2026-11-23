# Code 3 · A nota em JavaScript e em Python

A regra de nota do captador da Orbita, escrita duas vezes. Roda sem credencial nenhuma.

## O que faz

Cinco pedidos fictícios da Orbita passam por dois nós Code com a mesma regra. O de cima está em JavaScript, igual ao do captador. O de baixo está em Python. As notas e as faixas saem iguais nos dois.

| Pedido | Nota | Faixa |
|---|---|---|
| Marina Souza | 95 | quente |
| Pedro Lima | 55 | morno |
| Ana Paula Reis | 70 | quente |
| Rafa | 10 | frio |
| Lia, só com nome | 0 | frio |

## Como testar

Clique em **Execute workflow**. Abra **Nota em JavaScript** e depois **Nota em Python**. Nos dois, as notas são 95, 55, 70, 10 e 0, e as faixas são quente, morno, quente, frio e frio.

## O que treinar

1. Ache, nos dois códigos, a linha que dá 15 pontos ao e-mail de empresa.
2. Nos dois, faça o quente começar em 80. A Ana Paula, com 70, vira morno nos dois.
3. No nó Code, abra o campo **Language** e veja as duas opções. Quando troca a linguagem, o n8n guarda um código para cada uma.

## Erros comuns

No Python, o item da vez é `_item["json"]`, com colchetes e aspas. `$json` só existe no JavaScript.

No Python, o recuo no começo da linha faz parte do código. Linha fora do lugar dá erro.

No captador da aula a regra fica em JavaScript. O nó **Reunir pedido e cartão** busca dados de outro nó com `$('Lead qualificado')`, e o Python do n8n só enxerga o que entra nele.
