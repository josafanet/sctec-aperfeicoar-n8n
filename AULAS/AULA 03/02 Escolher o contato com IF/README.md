# 02 Escolher o contato com IF

Exemplo da aula 3 para treinar caminhos com IF.

## O que faz

Três contatos fictícios passam por dois IFs. Cada um termina com a ação que a equipe faria. O fluxo não envia mensagem nenhuma.

| Contato | WhatsApp | Autorizou | Ação esperada |
|---|---|---|---|
| Marina Souza | tem | sim | Chamar no WhatsApp |
| Pedro Lima | vazio | sim | Mandar e-mail |
| Rafa | tem | nao | Não entrar em contato |

## Como testar

Clique em **Execute workflow**. O número em cada ligação mostra quantos contatos passaram por ali. Abra os três nós do fim e leia o campo `acao`.

## O que treinar

1. Antes de rodar, preveja o caminho de cada contato.
2. No **Gatilho Manual**, mude o consentimento do Rafa para `sim` e rode de novo.
3. Apague o WhatsApp da Marina. Veja ela mudar de caminho.

## Erros comuns

Para o IF, `Sim` com letra maiúscula é diferente de `sim`. Padronize o texto antes ou ligue a opção **Ignore Case** do IF.

Um WhatsApp só com espaços conta como preenchido. Limpe o campo antes do IF.
