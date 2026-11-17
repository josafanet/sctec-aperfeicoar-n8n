# Orbita Labs v1

Primeira versão do projeto da Orbita Labs. A página da campanha envia o pedido do cliente para o n8n e o fluxo responde na hora agradecendo pelo nome

## O que tem no fluxo

O Disparo de Gatilho recebe o pedido por POST no caminho senai-orbita-v1. Ele aceita chamadas de qualquer origem para que o formulário do site consiga falar com o n8n

O Declarar Variaveis separa o campo nome que veio no corpo da requisição

O Resposta do Gatilho devolve um texto simples com a expressão abaixo

```
{{ 'Recebemos seu pedido, ' + String($json.nome ?? '').trim() + '!' }}
```

O ?? coloca um texto vazio quando o nome não vem, assim o fluxo não quebra. O String garante que o valor vire texto e o trim tira os espaços que sobram no começo e no fim

## Como testar

Importe, clique em Execute workflow e copie a Test URL do Disparo de Gatilho. Mande um POST com o nome no corpo

```bash
curl -X POST "COLE_A_TEST_URL_AQUI" -H "Content-Type: application/json" -d '{"nome":"  Ana  "}'
```

A resposta deve chegar como Recebemos seu pedido, Ana! sem os espaços extras. Teste também sem mandar o nome para ver o que acontece
