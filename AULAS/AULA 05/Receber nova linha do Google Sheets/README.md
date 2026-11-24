# Receber uma nova linha do Google Sheets

O n8n consulta a aba Pedidos uma vez por minuto. Quando alguém acrescenta uma linha, o último nó mostra quem fez o pedido. O fluxo só lê a planilha.

## Como testar

Abra um workflow novo no n8n. No menu **⋯**, escolha **Import from File** e selecione [o JSON deste exemplo](aula-04-nova-linha-no-sheets.json).

1. Abra a aba `Pedidos` da planilha de treino. Na linha 1, use os cabeçalhos `nome`, `email` e `empresa`. Deixe uma linha fictícia já preenchida, por exemplo `Ana de Teste`, `ana@example.com` e `Oficina de Teste`.
2. Em **Detectar nova linha**, autorize sua conta no campo de credencial do **Google Sheets Trigger**. Escolha a planilha em **Document**, a aba **Pedidos** em **Sheet** e confira **Trigger On → Row Added**.
3. Clique em **Execute workflow**. No teste manual, o gatilho pode devolver linhas que já estavam na aba. Abra **Ver pedido recebido → Output** e localize Ana. Guarde essa execução para consultar a amostra.
4. Para ver um evento novo, publique a cópia de treino. Aguarde 2 minutos para o gatilho registrar a posição inicial. Acrescente uma linha no fim da aba com `Bia de Teste`, `bia@example.com` e `Loja de Teste`.
5. Após a próxima consulta, abra **Executions**. Na execução automática, confira Bia em **Ver pedido recebido**. Para encerrar o treino, abra a seta ao lado de **Publish** e escolha **Unpublish**.

## O que treinar

Durante o teste da cópia publicada, acrescente outra linha pelo fluxo **Gravar um pedido no Google Sheets**. Em **Executions**, procure o nome que você acabou de gravar.

## Erros comuns

- Se faltar a credencial, abra o gatilho e autorize a mesma conta Google usada para acessar a planilha. O gatilho pede sua própria conexão.
- Se o evento não aparecer, confira se publicou o fluxo, escolheu a aba correta e acrescentou uma linha ao fim dos dados. Editar uma linha existente não aciona **Row Added**.
- Se precisar rever os campos antes da próxima consulta, abra a execução manual com a linha de Ana.

Consulte os [eventos do Google Sheets Trigger](https://docs.n8n.io/integrations/builtin/trigger-nodes/n8n-nodes-base.googlesheetstrigger/).
