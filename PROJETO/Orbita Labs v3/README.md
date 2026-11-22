# Orbita Labs v3

A Orbita no ponto em que a turma terminou a aula 3, em 19/11/2026.

## O que faz

É a Orbita como ficou no fim da aula 3. Recebe o pedido da página, trata os campos, grava na tabela `leads`, monta um resumo, avisa no Slack e responde à página.

Os nomes dos nós são os da turma. O que mudou desde a v2 está nos nós **Normalizar Dados**, **Adicionar Lead**, **Prepara Resumo**, **Avisar no Slack** e **Resposta do Gatilho**.

## Como testar

A tabela `leads` usa as colunas da v2 (`nome`, `email`, `whatsapp`, `empresa`, `porte`, `area`, `prazo` e `consentimento`, todas String) e mais `faturamento` como Number.

1. Na tabela `leads`, crie a coluna `faturamento` como **Number**. Escolha a tabela no **Adicionar Lead**.
2. No **Avisar no Slack**, escolha a sua credencial e o canal de teste.
3. Clique em **Execute workflow** e copie a Test URL do **Disparo de Gatilho**.
4. Na página da Orbita, abra **Configuração (para o aluno)** no rodapé, cole a URL e envie um pedido fictício.

[Página da Orbita Labs](https://orbita-automacao-gratuita.lovable.app/)

Também dá para mandar a chamada pelo [Postman](https://www.postman.com/downloads/), pelo [Insomnia](https://insomnia.rest/download) ou pelo [Thunder Client](https://marketplace.visualstudio.com/items?itemName=rangav.vscode-thunder-client), uma extensão do VS Code. Use a Test URL depois de clicar em Execute workflow, ou a Production URL depois de publicar o fluxo.

## O que treinar

1. Abra o **Normalizar Dados**. Veja o `trim()` no e-mail e o faturamento virar 0 quando a página não manda esse campo.
2. Abra o **Prepara Resumo**. Ele usa `$json`, que é sempre o nó anterior.
3. Abra a **Resposta do Gatilho**. O nó anterior agora é o Slack, então o nome vem de `$('Normalizar Dados')`.

## Erros comuns

Se a página mostra 404, a Test URL parou de escutar. Clique em **Execute workflow** de novo antes de enviar.

Se o **Adicionar Lead** reclama da coluna, falta criar `faturamento` como Number na tabela.

Ainda não há nota nem faixa. Essa regra entra na abertura da aula 4. Para treinar antes, use o exemplo 06 da aula 3.
