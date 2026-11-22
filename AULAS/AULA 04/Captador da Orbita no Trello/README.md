# Orbita Labs v4 · Do formulário ao cartão

Um cliente pede um diagnóstico na página da Orbita. O captador dá uma nota ao pedido e cria um cartão na lista **Novo lead**, com uma etiqueta de prioridade. Depois grava o pedido e o link do cartão na tabela `leads`. A confirmação aparece na página.

## Preparar sua cópia

1. Baixe [o JSON do captador](./aula-04-captador-da-turma.json). No n8n, crie um workflow em branco. No menu **⋯** do editor, escolha **Import from File** e abra o arquivo.
2. Na aba **Data tables** do mesmo projeto, abra ou crie a tabela `leads`. A v2 da turma já usava `nome`, `email`, `whatsapp`, `empresa`, `porte`, `area`, `prazo` e `consentimento`, todas **String** (texto). Para a v4, acrescente `nota` como **Number** (número) e `faixa`, `etapa`, `trello_id`, `trello_url` como **String**. No editor, abra **Adicionar Lead**. Em **Data table**, escolha **From list** e selecione sua tabela.
3. No seu quadro do Trello, localize a lista **Novo lead** e as etiquetas **quente**, **morno** e **frio**. Crie as que faltarem. No menu **⋯** do quadro, escolha **Imprimir, exportar e compartilhar → Exportar como JSON**. No arquivo, procure a lista em `lists` e as etiquetas em `labels`. Cada uma tem seu próprio campo `id`. Cole os quatro valores no nó **Configurar Trello**, em `lista_novo_lead`, `etiqueta_quente`, `etiqueta_morno` e `etiqueta_frio`.
4. Em **Criar cartão no Trello**, selecione sua credencial **Trello API**. Se precisar criá-la, abra **Credentials** no n8n. Salve a chave do seu Power-Up em **API Key** e o token do Trello em **API Token**. Use o guia para obtê-los. [Guia de credenciais do Trello no n8n](https://docs.n8n.io/integrations/builtin/credentials/trello/)

## Enviar um pedido

1. No editor, abra **Disparo de Gatilho** e copie a **Test URL**, que termina em `/orbita-v4`. Na página da campanha, abra **Configuração (para o aluno)** no rodapé e cole a URL em **Endereço que recebe os pedidos (webhook)**. [Página da Orbita Labs](https://orbita-automacao-gratuita.lovable.app/)
2. Preencha um pedido fictício da tabela abaixo. Nas linhas com travessão, deixe o campo vazio. Marque o consentimento no formulário completo. No editor, clique em **Execute workflow**. Volte à página e clique em **Agendar meu diagnóstico**. Repita a execução antes de cada envio.
3. Veja a confirmação na página. Na tabela `leads`, localize a linha pelo nome e abra `trello_url`. O cartão deve estar em **Novo lead**, com a mesma faixa da linha. Abra **Faixa** no editor para ver por qual das três saídas o pedido passou.

| Nome | E-mail | WhatsApp | Empresa |
|---|---|---|---|
| Marina Souza | MARINA@GrupoVale.com.br | (48) 99812-3344 | Grupo Vale Logística |
| Pedro Lima | pedro.lima@gmail.com | 48 3222 1100 | Lima Contabilidade |
| Ana Paula Reis | — | (48) 98877-6655 | Clínica Bem Estar |
| Rafa | rafa@hotmail.com | — | — |

| Nome | Tamanho da equipe | Área | Quando quer começar | Nota e etiqueta |
|---|---|---|---|---|
| Marina Souza | 51 a 200 pessoas | Atendimento | Ainda este mês | 95 · quente |
| Pedro Lima | 11 a 50 pessoas | Financeiro | No próximo trimestre | 55 · morno |
| Ana Paula Reis | 11 a 50 pessoas | Atendimento | Ainda este mês | 70 · quente |
| Rafa | 1 a 10 pessoas | Outra | Só estou pesquisando | 10 · frio |

Para o quinto teste, abra a versão curta da página. Confira a Test URL no rodapé, clique em **Execute workflow** e envie só o nome `Lia`. A resposta deve ser **Recebemos seu pedido, Lia! Nossa equipe entrará em contato.** O cartão deve ter a etiqueta **frio** e a linha deve mostrar **0**. [Formulário só com nome](https://orbita-automacao-gratuita.lovable.app/?etapa=1)

## O que treinar

- Preveja a nota da Marina antes de abrir **Nota do lead**. O prazo soma 40, o porte soma 20, o e-mail de empresa soma 15 e o WhatsApp e a empresa somam 10 cada.
- Abra **Faixa** e acompanhe o pedido da Rafa. As regras procuram `quente` e `morno`. O pedido frio passa por **Fallback**, a terceira saída.
- Abra a saída de **Criar cartão no Trello** e depois a de **Reunir pedido e cartão**. Na primeira, localize `url`. Na segunda, confira se `trello_url` tem o mesmo valor e se o nome do cliente voltou a aparecer.

## Se o teste parar

- **A página mostrou 404.** Copie a **Test URL** desta versão. Cole no rodapé e clique em **Execute workflow** de novo antes do envio.
- **O Trello recusou a criação do cartão.** Confira a credencial escolhida e o ID da lista. No JSON do quadro, copie `id` da lista **Novo lead**. O campo `idBoard` identifica o quadro inteiro.
- **A etiqueta veio errada.** Abra **Configurar Trello** e confira o ID da etiqueta que corresponde à faixa. Os quatro códigos devem vir do quadro em que o cartão será criado.
- **O cartão apareceu, mas a tabela ficou vazia.** Abra **Adicionar Lead**, confira a tabela, os nomes e os tipos das colunas. Se a troca de tabela apagou o mapeamento, arraste cada campo de **Reunir pedido e cartão** para a coluna de mesmo nome. Consulte o quadro antes de repetir o envio, pois um novo teste cria outro cartão.
