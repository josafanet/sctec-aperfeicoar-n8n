# HTTP com Basic Auth

Este exemplo mostra onde o HTTP Request usa usuário e senha para consultar uma API com Basic Auth. Você pode abrir a configuração sem fazer uma chamada.

## Como testar

Abra um workflow novo no n8n. No menu **⋯**, escolha **Import from File** e selecione [o JSON deste exemplo](aula-04-http-basic.json).

1. Abra **Consultar com Basic Auth** e localize **Authentication → Generic Credential Type** e **Generic Auth Type → Basic Auth**. O domínio com `.invalid` é fictício.
2. Para fazer uma chamada, obtenha na documentação da sua própria API de treino uma URL HTTPS de leitura (GET) que aceite Basic Auth. Cole essa URL no lugar do exemplo.
3. No campo de credencial, escolha **Create new credential**. Preencha **User** e **Password** com o usuário e a senha da sua API de treino. Salve a credencial e confira se ela ficou selecionada no nó.
4. Clique em **Execute workflow** e abra a saída da consulta. Compare o recurso recebido com o que a documentação da sua API descreve.

## O que treinar

Abra **Create new credential** e localize os dois campos que a API pede. Feche a janela se estiver só explorando o exemplo.

## Erros comuns

- Se o domínio ainda termina em `.invalid`, troque a URL inteira pelo endereço da API de treino.
- Em caso de 401, confira o usuário e a senha da conta na credencial.

Consulte os [tipos de autenticação do HTTP Request](https://docs.n8n.io/integrations/builtin/credentials/httprequest/).
