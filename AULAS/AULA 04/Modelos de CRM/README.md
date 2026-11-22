# Seu CRM da Orbita Labs

Escolha um dos dois modelos. A demonstração da aula 4 usa o **Trello**. No **Notion**, você recebe os mesmos cinco pedidos fictícios e acompanha em que etapa está cada conversa.

| Sua escolha | Arquivo para baixar | Onde abrir |
|---|---|---|
| Trello | [trello-orbita.json](trello-orbita.json) | No editor do **n8n**, em **⋯ → Import from File** |
| Notion | [notion-orbita.csv](notion-orbita.csv) | No **Notion** pelo computador, em **Configurações → Importar → CSV** |

No GitHub, abra o arquivo escolhido e clique no ícone de download **Download raw file**. Se recebeu a pasta em ZIP, extraia os arquivos no computador.

## Trello

**Prepare seu quadro.** No Trello, escolha **Criar → Criar quadro**. Use o seu espaço de trabalho, selecione **Privado** e dê o nome exato `Orbita Labs · Diagnósticos`. Comece com o quadro vazio. Se o Trello tiver criado listas de exemplo, confira se estão vazias e use **⋯ → Arquivar esta lista** em cada uma. Copie o endereço do quadro na barra do navegador.

**Conecte sua conta ao n8n** se você ainda não tem uma credencial **Trello API**.

1. No portal do Trello, escolha **New**, dê o nome `n8n curso`, selecione seu espaço de trabalho, deixe **iframe connector URL** em branco e preencha o contato. Clique em **Create**. [Portal de Power-Ups](https://trello.com/power-ups/admin)
2. Abra **API Key → Generate a new API Key**. Em **Allowed origins**, informe o endereço do seu n8n até o domínio, por exemplo `https://seunome.app.n8n.cloud`. Ao lado da chave, clique em **Token**. Confira as permissões de leitura e escrita e confirme em **Allow**.
3. No n8n, em **Credentials → Create credential → Trello API**, cole a chave em **API Key** e o token em **API Token**. Clique em **Save**. Guarde esses valores só na credencial. [Instruções do n8n](https://docs.n8n.io/integrations/builtin/credentials/trello/)

**Monte sua cópia.**

1. Crie um **workflow vazio** no n8n. Abra **⋯ → Import from File** e selecione `trello-orbita.json`. Você verá o fluxo *Orbita Labs · Montar meu quadro no Trello*. [Importar um workflow](https://docs.n8n.io/workflows/export-import/)
2. Abra **Meu quadro**. Em `endereco_quadro`, substitua `CONFIGURAR_URL_DO_QUADRO` pelo endereço copiado do Trello.
3. Abra **Ler quadro** e selecione sua credencial **Trello API**. Faça o mesmo em **Criar item que falta**. Volte ao editor e clique uma vez em **Execute workflow**.
4. Quando o nó **IDs para o captador** ficar verde, abra-o e consulte **Output → JSON**. Guarde `lista_novo_lead`, `etiqueta_quente`, `etiqueta_morno` e `etiqueta_frio` para configurar o captador. Abra o link do campo `quadro`.

No quadro, Bia deve estar em **Novo lead**, com a etiqueta **frio**. Há cinco cartões, um em cada lista. Se a montagem parou no meio, abra o nó vermelho e leia o erro. Depois de corrigir, use **Execute workflow** desde o início. Ele procura os itens existentes antes de criar os que faltam.

Para guardar uma segunda cópia pronta, use o menu do quadro **⋯ → Mais → Copiar quadro**, escolha o seu espaço e mantenha os cartões. Se ligar o captador à segunda cópia, obtenha os IDs dela. No menu dessa cópia, escolha **Imprimir, exportar e compartilhar → Exportar como JSON**. Em `lists`, localize o `id` da lista **Novo lead**. Em `labels`, consulte o `id` de cada faixa. [Copiar quadros](https://support.atlassian.com/trello/docs/copying-cards-lists-or-boards/) · [Exportar um quadro](https://support.atlassian.com/trello/docs/exporting-data-from-trello/)

## Notion

1. No computador, abra o Notion em **Configurações → Importar → CSV**. Selecione `notion-orbita.csv`, escolha **criar uma nova base de dados** e indique uma página no seu espaço privado. [Importar CSV](https://www.notion.com/help/import-data-into-notion#csv)
2. Na correspondência das colunas, escolha **Título** para `Lead`, **E-mail** para `E-mail`, **Telefone** para `WhatsApp` e **Número** para `Nota`. Use **Seleção** para `Porte`, `Área`, `Prazo`, `Faixa` e `Etapa`. Se a tabela já abriu, clique no cabeçalho de cada coluna e ajuste o tipo em **Editar propriedade**.
3. Dê à base o nome `Orbita Labs · Diagnósticos`. Ao lado da aba da tabela, clique em **+ → Quadro**. Nas configurações dessa visualização, escolha **Agrupar → Etapa** e mostre a propriedade **Faixa** nos cartões. [Visualização em quadro](https://www.notion.com/help/boards)
4. Arraste os títulos das colunas para esta ordem: **Novo lead → Contato feito → Diagnóstico agendado → Proposta → Fechado**. Confira se Bia está na primeira coluna e Lia na última.
5. Para guardar outra cópia, abra o menu **⋯** da página da base, escolha **Duplicar** e inclua o conteúdo, se essa opção aparecer. Abra a cópia e confira os cinco registros antes de editá-la.

A importação do CSV funciona sem credencial. Para criar novos pedidos automaticamente, conecte o n8n à sua cópia. No painel de integrações do Notion, crie uma integração interna no mesmo espaço e habilite leitura e inserção de conteúdo. Em **Secrets**, copie o **Internal Integration Token** para uma credencial **Notion API**, no campo **Internal Integration Secret** do n8n. Na página da base, abra **⋯ → Connections → Connect to** e selecione a integração. [Painel do Notion](https://www.notion.com/my-integrations) · [Credencial Notion no n8n](https://docs.n8n.io/integrations/builtin/credentials/notion/)

**Treino.** Mova Bia de **Novo lead** para **Contato feito**. Abra o cartão e confira a nota **35** e a faixa **frio**. A coluna registra o andamento da conversa. A faixa indica a prioridade calculada a partir do pedido.
