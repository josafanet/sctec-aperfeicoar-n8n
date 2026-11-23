# Switch 1 · Separar por texto

Primeiro contato com o Switch, antes do captador da Orbita. Roda sem credencial nenhuma.

## O que faz

Cinco chamados fictícios de atendimento passam pelo Switch **Qual setor?**. Cada um vai para a fila do setor escrito no chamado. O que não bate com nenhuma regra sai pela **Fallback**. O fluxo não envia nada.

| Cliente | Setor escrito no chamado | Fila esperada |
|---|---|---|
| Joana | `financeiro` | Fila do financeiro |
| Marcos | `suporte` | Fila do suporte |
| Lívia | `vendas` | Fila de vendas |
| Tiago | `Vendas` | Sem fila definida |
| Sueli | `rh` | Sem fila definida |

## Como testar

Clique em **Execute workflow**. O número em cada ligação mostra quantos chamados passaram por ali: 1 no financeiro, 1 no suporte, 1 em vendas e 2 em **Sem fila definida**.

## O que treinar

1. Antes de rodar, diga para qual fila vai cada chamado.
2. O chamado do Tiago ficou fora da fila de vendas. Abra o Switch, ligue **Ignore Case** em **Options** e rode de novo.
3. Crie uma quarta regra para `rh` e ligue a saída nova a um nó **No Operation**.

## Erros comuns

O Switch compara o texto exato. `Vendas` com letra maiúscula não é igual a `vendas`.

Se **Fallback Output** ficar em None, o chamado que não cumpre nenhuma regra some sem aviso.

O IF tem só duas saídas. Para três caminhos ou mais, um Switch substitui uma fila de IFs.
