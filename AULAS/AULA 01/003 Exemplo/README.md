# 003 Exemplo

Aqui o webhook passa a responder para quem chamou. O fluxo recebe um cadastro com nome e email por POST, organiza o nome e devolve uma mensagem de confirmação em texto

## O que tem no fluxo

O Disparo de Gatilho é um webhook que aceita POST no caminho cadastro. Ele está configurado para responder pelo nó Respond to Webhook e aceita chamadas de qualquer origem, o que permite usar ele a partir de uma página na internet

O Declarar Variaveis pega o nome que veio no corpo da requisição e guarda em pessoa.nome

O Resposta do Gatilho monta o texto final. O nome aparece em maiúsculas com toUpperCase e o email é buscado direto no primeiro nó com a expressão abaixo, já que ele não passou pelo Declarar Variaveis

```
{{ $('Disparo de Gatilho').item.json.body.email }}
```

## Como testar

Importe, clique em Execute workflow e copie a Test URL do Disparo de Gatilho. Mande um POST com um JSON parecido com este pelo Postman, pelo Insomnia ou pelo terminal

```bash
curl -X POST "COLE_A_TEST_URL_AQUI" -H "Content-Type: application/json" -d '{"nome":"Ana","email":"ana@exemplo.com"}'
```

A resposta volta com o nome em maiúsculas e o email informado. Vale reparar que o texto da resposta tem um errinho de digitação, um bom exercício é achar e corrigir no nó Resposta do Gatilho
