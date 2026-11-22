# Consultar feriados

A Orbita consulta os feriados nacionais antes de sugerir uma reunião. O nó HTTP Request faz uma leitura (GET) na BrasilAPI.

## Como testar

Abra um workflow novo no n8n. No menu **⋯**, escolha **Import from File** e selecione [o JSON deste exemplo](aula-04-consultar-feriados.json).

1. Abra **Buscar feriados**. Confira o método **GET**, a URL que termina em `/2026` e **Authentication → None**.
2. No canvas, clique em **Execute workflow**. Abra **Buscar feriados → Output → JSON** e procure `Natal`. No mesmo item, o campo `date` traz `2026-12-25`.

## O que treinar

Troque o ano no fim da URL por `2027`, rode o fluxo e encontre a data de Tiradentes. Depois, volte a URL para `2026`.

## Erros comuns

- Se aparecer 404, confira o caminho `/api/feriados/v1/2026` na URL.
- Se a chamada demorar ou retornar um erro de servidor, abra a mesma URL no navegador para conferir se a API responde.

Confira a [resposta da BrasilAPI para 2026](https://brasilapi.com.br/api/feriados/v1/2026).
