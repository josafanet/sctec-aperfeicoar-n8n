# 01 Testar sem preencher a página

Exemplo da aula 3 para testar o começo da Orbita sem abrir a página a cada vez.

## O que faz

O gatilho já tem um pedido fictício fixado. Assim o fluxo roda sem abrir a página e sem copiar a Test URL. Os nós **Variveis** e **Normalizar Dados** são os mesmos da Orbita da turma.

## Como testar

Clique em **Execute workflow**. Abra o **Normalizar Dados** e compare a entrada, à esquerda, com a saída, à direita.

Quando quiser testar com a página de verdade, solte os dados fixados, clique em Execute workflow e mande o pedido para a Test URL.

Também dá para mandar a chamada pelo [Postman](https://www.postman.com/downloads/), pelo [Insomnia](https://insomnia.rest/download) ou pelo [Thunder Client](https://marketplace.visualstudio.com/items?itemName=rangav.vscode-thunder-client), uma extensão do VS Code. Use a Test URL depois de clicar em Execute workflow, ou a Production URL depois de publicar o fluxo.

## O que treinar

1. Abra o **Disparo de Gatilho** e use o lápis da saída para editar os dados. Troque o nome por `JOCA da silva` e rode de novo.
2. Coloque espaços antes e depois do e-mail. Veja o `trim()` tirar os espaços.
3. Mande também `"faturamento": "1500"` dentro de `body`. Veja o campo virar número no **Variveis**.

## Erros comuns

Os dados fixados não mudam sozinhos. Se a página passou a mandar um campo novo, envie um pedido de verdade e fixe a saída de novo.

Se o **Variveis** mostra campos vazios, confira se os dados estão dentro de `body`.

Para voltar a receber pedidos da página, clique no alfinete da saída do gatilho e solte os dados.
