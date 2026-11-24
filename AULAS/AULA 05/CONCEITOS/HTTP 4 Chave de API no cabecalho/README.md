# HTTP 4 · Chave de API no cabeçalho

O terceiro jeito comum de se identificar numa API, depois de Basic e Bearer. Pede uma credencial de treino, que você cria em 1 minuto.

## O que faz

Muitas APIs entregam uma chave e pedem que ela vá num cabeçalho da chamada, como `X-API-Key`. Este exemplo guarda a chave numa credencial **Header Auth** e chama o httpbin.org, um serviço público de teste que devolve os cabeçalhos recebidos. Assim dá para ver a chave chegando do outro lado.

| Jeito | O que a credencial guarda | O que vai na chamada |
|---|---|---|
| Basic Auth | User e Password | cabeçalho `Authorization: Basic ...` |
| Bearer Auth | Bearer Token | cabeçalho `Authorization: Bearer ...` |
| Header Auth | Name e Value | um cabeçalho com o nome que a API pede |

## Como testar

Abra o **Consultar com chave de API**. No campo de credencial, escolha **Create new credential**. Em **Name**, escreva `X-API-Key`. Em **Value**, escreva `chave-de-treino-123`. Salve e clique em **Execute workflow**. Na saída, dentro de `headers`, aparece `X-Api-Key` com o valor da credencial.

## O que treinar

1. Compare com **HTTP com Basic Auth** e **HTTP com Bearer**. No nó, só o **Generic Auth Type** muda.
2. Mude o **Value** da credencial e rode de novo. O valor novo aparece na resposta.
3. Baixe este fluxo pelo menu **⋯ → Download** e abra o arquivo. A chave não está lá. O JSON guarda só o nome da credencial.

## Erros comuns

O nome do cabeçalho é a API que escolhe. `X-API-Key` é comum, mas confira na documentação.

A chave fica na credencial, nunca num campo do nó. O que está no nó vai junto quando o fluxo é compartilhado.

O httpbin.org aceita qualquer chave. Uma API de verdade responde 401 ou 403 quando a chave está errada.
