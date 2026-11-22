# HTTP com Bearer Auth

Este exemplo mostra onde o HTTP Request usa um token de acesso para consultar uma API com Bearer Auth. Você pode abrir a configuração sem fazer uma chamada.

## Como testar

Abra um workflow novo no n8n. No menu **⋯**, escolha **Import from File** e selecione [o JSON deste exemplo](aula-04-http-bearer.json).

1. Abra **Consultar com Bearer Auth** e localize **Authentication → Generic Credential Type** e **Generic Auth Type → Bearer Auth**. O domínio com `.invalid` é fictício.
2. Para fazer uma chamada, obtenha na documentação da sua própria API de treino uma URL HTTPS de leitura (GET) que aceite Bearer Auth. Cole essa URL no lugar do exemplo.
3. No campo de credencial, escolha **Create new credential**. Em **Bearer Token**, informe apenas o token da sua API de treino. O nó acrescenta o prefixo Bearer ao enviar. Salve a credencial e confira se ela ficou selecionada no nó.
4. Clique em **Execute workflow** e abra a saída da consulta. Compare o recurso recebido com o que a documentação da sua API descreve.

## O que treinar

Abra **Create new credential** e localize o campo do token. Feche a janela se estiver só explorando o exemplo.

## Erros comuns

- Se o domínio ainda termina em `.invalid`, troque a URL inteira pelo endereço da API de treino.
- Em caso de 401, confira a validade do token e se o campo contém apenas o valor, sem a palavra Bearer.

Consulte os [tipos de autenticação do HTTP Request](https://docs.n8n.io/integrations/builtin/credentials/httprequest/).
