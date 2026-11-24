# Resumo diário de leads

Às 08h de Brasília (07h em Campo Grande), o fluxo conta quantos pedidos entraram no dia anterior. O comercial pode abrir a execução e ver o total por faixa.

## Como testar

Abra um workflow novo no n8n. No menu **⋯**, escolha **Import from File** e selecione [o JSON deste exemplo](aula-04-resumo-diario-de-leads.json).

1. Em **Ler leads → Data table**, escolha **From list** e selecione sua tabela `leads`. Ela precisa ter a coluna de texto `faixa`. O próprio n8n preenche `createdAt` quando uma linha entra.
2. Em **Escolher dia**, use `0` em `dias_atras`. Abra a tabela de treino em **Data tables** e acrescente uma linha fictícia com `faixa = quente`. Conte as linhas criadas no dia.
3. Clique em **Execute workflow** e abra **Contar por faixa → Output**. A linha que você acrescentou entra no total e em `quente`. Uma linha sem faixa entra em `sem_faixa`. Sem pedidos no período, o fluxo devolve `total = 0`.
4. Para ver o relógio disparar, use uma cópia de treino. Em **Horário do resumo**, mude a única regra para **Minutes**, com intervalo **1**. Publique a cópia, espere uma execução aparecer em **Executions** e abra a seta ao lado de **Publish** e escolha **Unpublish**.
5. Na cópia, restaure **Days**, intervalo **1**, hora **8**, minuto **0**, e volte `dias_atras` para `1`. Essa é a configuração diária.

## O que treinar

Na tabela de treino, acrescente pedidos com outra faixa e com a faixa em branco. Rode com `dias_atras = 0` e confira se a soma das quatro contagens bate com o total.

## Erros comuns

- Se a tabela não abrir, confira se **Ler leads** aponta para a tabela do seu projeto.
- Um total zero pode estar correto. Confira a data em `dia` e o horário de criação das linhas. Uma alteração em uma linha antiga conserva a data de criação.
- O relógio automático exige o workflow publicado. Para testar de imediato no editor, use **Execute workflow**.

Consulte os guias de [agendamento](https://docs.n8n.io/integrations/builtin/core-nodes/n8n-nodes-base.scheduletrigger/) e de [operações com linhas](https://docs.n8n.io/integrations/builtin/core-nodes/n8n-nodes-base.datatable/rows/).
