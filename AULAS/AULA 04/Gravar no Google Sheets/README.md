# Gravar um pedido no Google Sheets

Cada execução acrescenta um pedido fictício ao fim da aba Pedidos. O Google Sheets recebe os três campos preparados no nó Pedido fictício.

## Como testar

Abra um workflow novo no n8n. No menu **⋯**, escolha **Import from File** e selecione [o JSON deste exemplo](aula-04-gravar-no-sheets.json).

1. No Google Sheets, crie uma planilha de treino e renomeie uma aba para `Pedidos`. Na linha 1, escreva `nome` em A1, `email` em B1 e `empresa` em C1.
2. Em **Acrescentar linha**, deixe **Authentication → OAuth2**. Abra a lista de credenciais e autorize uma conta Google com acesso de edição à sua planilha.
3. Ainda no nó, escolha a planilha em **Document → From list** e a aba **Pedidos** em **Sheet → From list**. Mantenha **Append Row** e **Map Automatically**.
4. Clique em **Execute workflow**. Abra a aba **Pedidos** no navegador e confira a nova linha com `Ana de Teste`, `ana@example.com` e `Oficina de Teste`.

## O que treinar

Em **Pedido fictício**, mude o nome e a empresa. Execute de novo e confira as duas linhas na planilha. Você pode usar essa aba no exemplo do gatilho de nova linha.

## Erros comuns

- Se o documento não aparecer, confira a conta Google escolhida na credencial e se ela pode editar a planilha.
- Se o mapeamento acusar um campo desconhecido, compare os nomes da linha 1 com os campos do pedido. Use `email` sem hífen e em minúsculas.
- Cada clique em **Execute workflow** cria outra linha, mesmo se o pedido for igual.

Consulte a operação [Append Row do Google Sheets](https://docs.n8n.io/integrations/builtin/app-nodes/n8n-nodes-base.googlesheets/sheet-operations/#append-row).
