# Alerta de erro

Quando um fluxo **publicado** falha, este fluxo grava uma linha na tabela `erros`, com a hora, o fluxo, o nó, a mensagem e o link da execução.

## Preparar

1. Na aba **Data tables**, crie a tabela `erros` com as colunas `quando`, `workflow`, `no`, `mensagem` e `link`, todas **String**.
2. Importe [o JSON deste exemplo](aula-05-alerta-de-erro.json). Em **Registrar erro**, escolha a tabela `erros` e salve.
3. No captador v5, abra **Settings** e escolha este fluxo em **Error workflow**.

## Testar

O gatilho **Error Trigger** não dispara em execução manual. Ele roda só quando um fluxo publicado falha. Publique o captador e o alerta. Troque por um momento o ID da lista em **Configurar Trello** por um valor errado, publique e envie um pedido com um e-mail novo. A página recebe 502 e a tabela `erros` ganha uma linha. Depois desfaça a troca e publique de novo.
