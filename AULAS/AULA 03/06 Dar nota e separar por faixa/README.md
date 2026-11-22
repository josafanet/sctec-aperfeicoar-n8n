# 06 Dar nota e separar por faixa

Complemento da aula 3. A regra de pontuação ficou para a abertura da aula 4, e este exemplo deixa ela pronta para testar.

## O que faz

Cinco pedidos fictícios da Orbita ganham uma nota de 0 a 100. O Switch **Faixa** manda cada um para quente, morno ou frio.

Como a nota é somada. Prazo vale até 40 (este mês 40, próximo trimestre 25, pesquisando 5). Porte vale até 25 (200+ 25, 51 a 200 20, 11 a 50 10, 1 a 10 5). E-mail de empresa vale 15. WhatsApp e empresa valem 10 cada.

## Como testar

Clique em **Execute workflow**. Nas saídas da **Faixa**, devem passar 2 pedidos em quente, 1 em morno e 2 em frio. Abra o **Nota do lead** e confira as notas 95, 55, 70, 10 e 0.

| Pedido | Nota | Faixa |
|---|---|---|
| Marina Souza | 95 | quente |
| Pedro Lima | 55 | morno |
| Ana Paula Reis | 70 | quente |
| Rafa | 10 | frio |
| Lia, só com nome | 0 | frio |

## O que treinar

1. Antes de abrir o **Nota do lead**, calcule a nota do Pedro com a tabela da nota ao lado.
2. No **Gatilho Manual**, mude o prazo do Pedro para `este-mes`. A nota sobe para 70 e ele vira quente.
3. No código, faça o quente começar em 80. Veja a Ana Paula, com 70, passar para morno.

## Erros comuns

O Switch compara o texto exato. `Quente` com letra maiúscula não é igual a `quente`.

O pedido frio sai pela terceira saída, a **Fallback**. Se a opção **Fallback Output** ficar em None, o pedido que não cumpre nenhuma regra some.

Pedido sem e-mail ou sem empresa não dá erro. O campo vazio só deixa de somar pontos.
