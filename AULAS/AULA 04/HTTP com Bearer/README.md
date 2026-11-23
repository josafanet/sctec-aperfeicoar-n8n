# HTTP com Bearer Auth

Este exemplo mostra onde o HTTP Request guarda um token de acesso para consultar uma API com Bearer Auth. A chamada vai para o [httpbin.org](https://httpbin.org/), um serviço público de teste. Você não precisa de conta em lugar nenhum.

## Como testar

Abra um workflow novo no n8n. No menu **⋯**, escolha **Import from File** e selecione [o JSON deste exemplo](aula-04-http-bearer.json).

1. Abra **Consultar com Bearer Auth** e localize **Authentication → Generic Credential Type** e **Generic Auth Type → Bearer Auth**.
2. No campo de credencial, escolha **Create new credential**. Em **Bearer Token**, escreva `token-de-treino-123`. Salve e confira se a credencial ficou selecionada no nó.
3. Clique em **Execute workflow** e abra a saída da consulta. Ela traz `authenticated: true` e, em `token`, o valor que você digitou.

O httpbin.org aceita qualquer token e devolve o que recebeu. Uma API de verdade responde 401 quando o token está errado ou vencido.

## O que treinar

1. Troque o token por outro texto e rode de novo. O valor novo aparece na resposta.
2. Compare com o exemplo **HTTP com Basic Auth**. No nó, só o **Generic Auth Type** muda.

## Erros comuns

- No campo vai só o token, sem a palavra Bearer. O nó acrescenta o prefixo ao enviar.
- Se a chamada demorar ou der erro de servidor, o serviço de teste pode estar fora do ar. Espere um minuto e rode de novo.

Consulte os [tipos de autenticação do HTTP Request](https://docs.n8n.io/integrations/builtin/credentials/httprequest/).
