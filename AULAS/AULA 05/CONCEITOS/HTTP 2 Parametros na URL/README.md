# HTTP 2 · Parâmetros na URL

O HTTP Request com Query Parameters, numa API pública de clima. Roda sem credencial nenhuma.

## O que faz

Duas cidades chegam com latitude e longitude. O **Buscar clima** consulta a Open-Meteo, uma API pública de previsão do tempo. Os valores não ficam escritos na URL. Cada um entra numa linha de **Query Parameters**, e o n8n monta o endereço com `?` e `&`. O **Resumir clima** fica só com a temperatura e a chuva de agora.

| Parâmetro | Valor |
|---|---|
| `latitude` | a latitude da cidade, vinda do item |
| `longitude` | a longitude da cidade, vinda do item |
| `current` | `temperature_2m,precipitation` |
| `timezone` | `America/Sao_Paulo` |

## Como testar

Clique em **Execute workflow**. O **Resumir clima** devolve um item por cidade, com `temperatura`, `chuva_mm` e `medido_em`. Os números mudam a cada execução, porque são do momento da consulta.

## O que treinar

1. Abra o **Buscar clima** e conte as linhas de **Query Parameters**. Cada linha vira um pedaço `nome=valor` da URL.
2. No **Gatilho Manual**, acrescente a sua cidade, com a latitude e a longitude dela.
3. No parâmetro `current`, acrescente `,wind_speed_10m` e ache a velocidade do vento na saída do **Buscar clima**.

## Erros comuns

Latitude e longitude usam ponto, não vírgula: `-27.5954`.

No exemplo **HTTP 1**, o valor vai no caminho da URL. Aqui vai depois do `?`. A documentação de cada API diz qual dos dois ela usa.

Um valor que a API não conhece no `current` faz ela responder 400. Confira a grafia na documentação.
