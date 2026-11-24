# Subfluxo de leads

Um subfluxo é um fluxo sem gatilho próprio. Ele roda quando outro fluxo o chama, com uma entrada e uma saída combinadas.

- [Subfluxo · Consultar leads por faixa](aula-05-subfluxo-consultar-leads.json) recebe `faixa` e devolve `faixa`, `total` e a lista `leads`. Os seis leads são fictícios e ficam no código, para o exemplo rodar sem tabela.
- [Chamar o subfluxo de leads](aula-05-chamar-subfluxo.json) escolhe a faixa, chama o subfluxo e monta um resumo.

## Como testar

1. Importe o subfluxo e salve.
2. Importe o fluxo que chama. Em **Consultar leads por faixa**, escolha o subfluxo em **From list**.
3. Clique em **Execute workflow**. O resultado esperado é `3 leads na faixa quente. Marina Souza, Júlia Ramos, Ana Paula Reis`.

| Faixa | Total |
|---|---|
| `quente` | 3 |
| `morno` | 2 |
| `frio` | 1 |
| `todas` | 6 |

Troque a faixa em **Escolher a faixa** e tente prever o resultado antes de executar. Se o subfluxo não aparecer na lista, salve-o de novo. Se ainda não aparecer, publique-o.
