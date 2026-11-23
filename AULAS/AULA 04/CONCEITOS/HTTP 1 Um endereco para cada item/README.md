# HTTP 1 · Um endereço para cada item

O HTTP Request com um valor do item dentro da URL. Roda sem credencial nenhuma.

## O que faz

Três clientes fictícios chegam só com o CEP. O **Buscar endereço** consulta a BrasilAPI uma vez para cada cliente, porque o CEP entra na URL por uma expressão. O **Montar endereço** junta o nome do cliente com a rua, o bairro e a cidade que a API devolveu.

| Cliente | CEP | Endereço esperado |
|---|---|---|
| Bia | 88010400 | Praça Quinze de Novembro, Centro, Florianópolis/SC |
| Caio | 79002070 | Avenida Afonso Pena, Centro, Campo Grande/MS |
| Dani | 01001000 | Praça da Sé, Sé, São Paulo/SP |

## Como testar

Clique em **Execute workflow**. No **Buscar endereço**, entram 3 itens e saem 3, cada um com `street`, `neighborhood`, `city` e `state`. No **Montar endereço**, leia o campo `endereco` de cada cliente.

## O que treinar

1. Abra o **Buscar endereço** e ache a expressão `{{ $json.cep }}` no fim da URL.
2. No **Gatilho Manual**, acrescente um quarto cliente com o CEP da sua rua e rode de novo.
3. Troque um CEP por `00000000` e rode. A API responde 404 e o fluxo para nesse nó. Volte o CEP.

## Erros comuns

A saída do HTTP Request é a resposta da API. O nome do cliente não vem junto. Por isso o **Montar endereço** busca o nome com `$('Gatilho Manual').item.json.cliente`.

O CEP vai só com os oito dígitos, sem traço e sem ponto.

Se a chamada demorar ou der erro de servidor, abra a mesma URL no navegador para ver se a API responde.
