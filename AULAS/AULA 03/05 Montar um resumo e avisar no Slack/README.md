# 05 Montar um resumo e avisar no Slack

Exemplo da aula 3 para montar uma mensagem com expressões e enviar no Slack.

## O que faz

Junta nome, e-mail e celular de um lead fictício num texto só. Depois manda esse texto para um canal do Slack. O texto fica no campo `resumo do lead` do nó **Prepara Resumo**, como na aula.

## Como testar

Crie um canal de teste no seu Slack antes de começar.

1. Clique no botão de play do **Prepara Resumo** para rodar só até ele. Leia o texto em `resumo do lead`.
2. No **Avisar no Slack**, escolha a sua credencial e o canal de teste.
3. Clique em **Execute workflow** e veja a mensagem chegar no canal.

## O que treinar

1. Acrescente a empresa ao resumo. O campo `empresa` já vem no **Gatilho Manual**.
2. Acrescente o link do WhatsApp. Escreva `https://wa.me/55` e arraste o campo `whatsapp` logo depois.
3. Mande o texto direto no Slack, sem o **Prepara Resumo**. Compare qual jeito fica mais fácil de mudar depois.

## Erros comuns

O Slack pede credencial. Crie a sua em **Credentials** e escolha no nó. Na aula, a autorização foi feita pela conta do Slack.

Se o Slack não achar o canal, escolha o canal pela lista (**From list**) em vez de digitar o nome.

A opção **Include Link to Workflow** já está desligada. Ligada, ela acrescenta um link do n8n no fim da mensagem.
