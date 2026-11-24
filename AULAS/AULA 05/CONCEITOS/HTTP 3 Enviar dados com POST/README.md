# HTTP 3 · Enviar dados com POST

O HTTP Request mandando dados, em vez de só ler. Roda sem credencial nenhuma.

## O que faz

Um pedido fictício da Orbita é enviado por POST para o httpbin.org, um serviço público de teste que devolve tudo o que recebeu. É o caminho inverso do captador. Lá, a página manda o pedido para o seu webhook. Aqui, quem manda é o n8n. O **Ler o que chegou** mostra o corpo que o servidor recebeu.

## Como testar

Clique em **Execute workflow**. Na saída do **Enviar pedido**, o campo `json` traz o nome, o e-mail e a empresa que saíram do n8n. No **Ler o que chegou**, o campo `tipo_do_corpo` mostra `application/json`.

## O que treinar

1. Abra o **Enviar pedido** e ache **Send Body**. Cada linha de **Body Parameters** vira um campo do JSON enviado.
2. Acrescente uma linha com o nome `prazo` e o valor `{{ $json.prazo }}`. Rode e confira o campo novo na resposta.
3. Troque o método para **GET** e rode. O httpbin.org responde 405, porque esse endereço só aceita POST. Volte para **POST**.

## Erros comuns

GET lê, POST envia. O método tem de ser o que a documentação da API pede.

Com **Send Body** desligado, o POST sai vazio.

O httpbin.org só devolve o que recebe e é público. Use só dados fictícios.
