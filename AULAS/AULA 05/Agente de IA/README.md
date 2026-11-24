# Agente de IA

Dois fluxos com o mesmo agente. O primeiro só conversa. O segundo pode chamar o [subfluxo de leads](../Subfluxo%20de%20leads/README.md) como ferramenta.

- [Agente 1 · Conversa simples](aula-05-agente-conversa-simples.json)
- [Agente 2 · Com a consulta de leads](aula-05-agente-com-consulta.json)

## Preparar

1. Importe o fluxo. Em **Modelo de linguagem**, escolha ou crie a credencial da OpenAI. No n8n Cloud, a opção de créditos gratuitos aparece na criação da credencial.
2. No Agente 2, importe antes o subfluxo e escolha-o em **Consultar leads por faixa**, na lista **From list**.

## Como testar

1. No Agente 1, clique em **Open chat** e escreva `Oi, o que a Orbita Labs faz?`. Depois pergunte `Quais leads quentes temos hoje?`. Ele não tem acesso aos dados e deve dizer que não sabe.
2. No Agente 2, faça a mesma pergunta. Abra a execução e veja a chamada da ferramenta, a faixa que o agente escolheu e o que o subfluxo devolveu. Devem aparecer Marina Souza, Júlia Ramos e Ana Paula Reis.
3. Pergunte por um lead que não existe. O agente deve dizer que não encontrou.

## O que observar

O agente escolhe a faixa sozinho, pela expressão `$fromAI('faixa', ...)`. A descrição da ferramenta e a mensagem de sistema fazem parte do pedido ao modelo. Se ele inventar um nome, releia as duas. O agente só consulta. Ele não grava nada nem manda mensagem.
