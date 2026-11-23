# Aula 4 · Conceitos antes do captador

Exemplos curtos para entender um nó de cada vez, antes de abrir o captador da Orbita. Todos começam por um **Gatilho Manual**, quase sempre com dados fictícios já fixados. Nenhum pede tabela ou conta em outro serviço. Só o **HTTP 4** pede uma credencial, com valores de treino que estão no próprio exemplo.

Para testar, importe o JSON, clique em **Execute workflow** e compare com o resultado esperado no README da pasta. A nota **Leia primeiro** do próprio fluxo traz o mesmo passo a passo.

## Nó Code

| Ordem | Exemplo | O que mostra |
|---|---|---|
| 1 | [Code 1 · Um item por vez](Code%201%20Um%20item%20por%20vez/README.md) | O código roda uma vez para cada item e acrescenta campos. Usa `$json` |
| 2 | [Code 2 · Todos os itens de uma vez](Code%202%20Todos%20os%20itens%20de%20uma%20vez/README.md) | O código recebe a lista inteira e devolve um resumo. Usa `$input.all()` |
| 3 | [Code 3 · A nota em JavaScript e em Python](Code%203%20A%20nota%20em%20JavaScript%20e%20em%20Python/README.md) | A regra de nota do captador escrita nas duas linguagens, lado a lado |
| 4 | [Code 4 · A mesma nota sem o nó Code](Code%204%20A%20mesma%20nota%20sem%20o%20Code/README.md) | A mesma regra só com Switch, IF e Edit Fields: 25 nós no lugar de 1 |

## Nó Switch

| Ordem | Exemplo | O que mostra |
|---|---|---|
| 1 | [Switch 1 · Separar por texto](Switch%201%20Separar%20por%20texto/README.md) | Uma saída para cada setor e a saída Fallback para o que sobrou |
| 2 | [Switch 2 · Separar por faixa de número](Switch%202%20Separar%20por%20faixa%20de%20numero/README.md) | Comparação de número e por que a ordem das regras conta |

Na aula 3 há mais dois exemplos do mesmo assunto: [02 Escolher o contato com IF](../../AULA%2003/02%20Escolher%20o%20contato%20com%20IF/README.md) e [06 Dar nota e separar por faixa](../../AULA%2003/06%20Dar%20nota%20e%20separar%20por%20faixa/README.md), que já junta o Code com o Switch.

## Nós Filter e Loop Over Items

| Exemplo | O que mostra |
|---|---|
| [Filter · Ficar só com o que interessa](Filter%20Ficar%20so%20com%20o%20que%20interessa/README.md) | O Filter ao lado de um IF com a mesma pergunta. O IF tem duas saídas, o Filter tem uma |
| [Loop · Processar em lotes](Loop%20Processar%20em%20lotes/README.md) | O n8n já repete a ação para cada item. O Loop Over Items entra para dividir em lotes |

## Nó HTTP Request

| Ordem | Exemplo | O que mostra |
|---|---|---|
| 1 | [HTTP 1 · Um endereço para cada item](HTTP%201%20Um%20endereco%20para%20cada%20item/README.md) | Um valor do item dentro da URL: um CEP por cliente, uma chamada por item |
| 2 | [HTTP 2 · Parâmetros na URL](HTTP%202%20Parametros%20na%20URL/README.md) | Query Parameters numa API pública de clima |
| 3 | [HTTP 3 · Enviar dados com POST](HTTP%203%20Enviar%20dados%20com%20POST/README.md) | O n8n mandando um pedido no corpo da chamada |
| 4 | [HTTP 4 · Chave de API no cabeçalho](HTTP%204%20Chave%20de%20API%20no%20cabecalho/README.md) | A credencial Header Auth. Pede uma credencial de treino |

Os três primeiros rodam sem credencial. Para usuário e senha ou token, veja [HTTP com Basic Auth](../HTTP%20com%20Basic%20Auth/README.md) e [HTTP com Bearer](../HTTP%20com%20Bearer/README.md), que usam o mesmo serviço público de teste do exemplo 4. A primeira consulta da aula é o [Consultar feriados](../Consultar%20feriados/README.md).

## Quando usar cada nó

| Preciso de | Nó |
|---|---|
| Dois caminhos, sim ou não | IF |
| Três caminhos ou mais | Switch |
| Seguir só com parte dos itens | Filter |
| Uma conta ou uma regra com muitos casos | Code, ou uma expressão num Edit Fields |
| Tratar os itens em lotes, com pausa entre eles | Loop Over Items |
| Ler ou enviar dados de outro sistema que não tem nó próprio | HTTP Request |
