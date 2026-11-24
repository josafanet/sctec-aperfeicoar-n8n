# Enviar os pedidos de teste

Este fluxo manda cinco pedidos ao seu captador v5, um de cada vez, e mostra o código e a resposta de cada um. A tabela que sai no fim serve de evidência das validações do projeto.

## Como testar

1. Publique o seu captador v5 e copie a **Production URL** do gatilho.
2. Importe [o JSON deste exemplo](aula-05-enviar-pedidos-de-teste.json) e cole a URL em **Endereço do captador**.
3. Clique em **Execute workflow** e abra **Ler a resposta**.

| Caso | Código esperado |
|---|---|
| Pedido válido | 200 |
| Nome vazio | 400 |
| E-mail inválido | 400 |
| Campo isca preenchido | 200, sem gravar |
| Mesmo pedido de novo | 200, pedido repetido |

Confira no quadro que existe um cartão só. A Test URL atende uma chamada por clique em **Execute workflow**, por isso este fluxo usa a Production URL.
