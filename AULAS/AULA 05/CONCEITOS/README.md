# Aula 5 · Loop e HTTP Request

Exemplos curtos para entender o Loop Over Items e o HTTP Request, antes de abrir o captador da Orbita. Todos começam por um **Gatilho Manual**, quase sempre com dados fictícios já fixados. Nenhum pede tabela ou conta em outro serviço. Só o HTTP 4 pede uma credencial, com valores de treino que estão no próprio exemplo.

Para testar, importe o JSON, clique em **Execute workflow** e compare com o resultado esperado no README da pasta. A nota **Leia primeiro** do próprio fluxo traz o mesmo passo a passo.

## Nó Loop Over Items

| Exemplo | O que mostra |
|---|---|
| [Loop · Processar em lotes](Loop%20Processar%20em%20lotes/README.md) | O n8n já repete a ação para cada item. O Loop Over Items entra para dividir em lotes |

## Nó HTTP Request

| Ordem | Exemplo | O que mostra |
|---|---|---|
| 1 | [HTTP 1 · Um endereço para cada item](HTTP%201%20Um%20endereco%20para%20cada%20item/README.md) | Um valor do item dentro da URL, como um CEP por cliente, com uma chamada por item |
| 2 | [HTTP 2 · Parâmetros na URL](HTTP%202%20Parametros%20na%20URL/README.md) | Query Parameters numa API pública de clima |
| 3 | [HTTP 3 · Enviar dados com POST](HTTP%203%20Enviar%20dados%20com%20POST/README.md) | O n8n mandando um pedido no corpo da chamada |
| 4 | [HTTP 4 · Chave de API no cabeçalho](HTTP%204%20Chave%20de%20API%20no%20cabecalho/README.md) | A credencial Header Auth. Pede uma credencial de treino |

Os três primeiros rodam sem credencial. Para usuário e senha ou token, veja [HTTP com Basic Auth](../HTTP%20com%20Basic%20Auth/README.md) e [HTTP com Bearer](../HTTP%20com%20Bearer/README.md), que usam o mesmo serviço público de teste do exemplo 4. A primeira consulta da aula é o [Consultar feriados](../Consultar%20feriados/README.md).

## Quando usar cada nó

| Preciso de | Nó |
|---|---|
| Tratar os itens em lotes, com pausa entre eles | Loop Over Items |
| Ler ou enviar dados de outro sistema que não tem nó próprio | HTTP Request |

Os nós Code, Switch e Filter estão em [Conceitos da aula 4](../../AULA%2004/CONCEITOS/README.md).
