# HTTP com Basic Auth

Este exemplo mostra onde o HTTP Request guarda usuário e senha para consultar uma API com Basic Auth. A chamada vai para o [httpbin.org](https://httpbin.org/), um serviço público de teste. Você não precisa de conta em lugar nenhum.

## Como testar

Abra um workflow novo no n8n. No menu **⋯**, escolha **Import from File** e selecione [o JSON deste exemplo](aula-04-http-basic.json).

1. Abra **Consultar com Basic Auth** e localize **Authentication → Generic Credential Type** e **Generic Auth Type → Basic Auth**.
2. No campo de credencial, escolha **Create new credential**. Em **User**, escreva `aluno`. Em **Password**, escreva `senha-de-treino`. Salve e confira se a credencial ficou selecionada no nó.
3. Clique em **Execute workflow** e abra a saída da consulta. Ela traz `authenticated: true` e `user: aluno`.

O usuário e a senha de treino estão escritos na própria URL, `/basic-auth/aluno/senha-de-treino`. O httpbin.org aceita o par que estiver ali. Numa API de verdade, a senha nunca aparece na URL nem no canvas.

## O que treinar

1. Troque a senha da credencial por outra qualquer e rode de novo. A API responde 401. Volte a senha certa.
2. Abra a credencial salva. O n8n não mostra mais a senha que você digitou.

## Erros comuns

- Resposta 401 significa que a API recusou o usuário ou a senha. Confira os dois na credencial.
- Se a chamada demorar ou der erro de servidor, o serviço de teste pode estar fora do ar. Espere um minuto e rode de novo.

Consulte os [tipos de autenticação do HTTP Request](https://docs.n8n.io/integrations/builtin/credentials/httprequest/).
