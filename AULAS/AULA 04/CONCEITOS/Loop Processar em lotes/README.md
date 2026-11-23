# Loop · Processar em lotes

Quando o n8n já repete sozinho e quando o Loop Over Items entra. Roda sem credencial nenhuma.

## O que faz

Seis contatos fictícios vão receber um aviso de matrícula. No caminho de cima, o **Montar mensagem** roda para os seis de uma vez, sem laço, porque todo nó do n8n já repete a ação para cada item. No caminho de baixo, o Loop Over Items **De 2 em 2** entrega dois contatos por vez e espera 2 segundos entre os lotes. É o jeito de respeitar o limite de envios de um serviço. Nada é enviado de verdade.

| Nó | O que esperar |
|---|---|
| Montar mensagem | 1 execução com 6 itens |
| Preparar envio | 3 execuções com 2 itens, com `lote` 1, 2 e 3 |
| Todos enviados | 6 itens, depois do último lote |

## Como testar

Clique em **Execute workflow** e espere uns 6 segundos. No **Montar mensagem**, os 6 contatos saem numa execução só. No **Preparar envio**, o seletor **Run 1 of 3** mostra três lotes de 2 contatos, com o campo `lote` em 1, 2 e 3. O **Todos enviados** recebe os 6 no fim.

## O que treinar

1. Antes de rodar, diga quantas vezes o **Preparar envio** vai rodar.
2. No **De 2 em 2**, mude **Batch Size** para 3 e rode. Quantos lotes aparecem?
3. Mude **Batch Size** para 1. O fluxo passa a tratar um contato por vez.

## Erros comuns

O último nó do laço precisa voltar para o Loop Over Items. Sem essa ligação, só o primeiro lote roda.

A saída **done** só recebe os itens quando todos os lotes terminam. O que vem depois do laço fica ligado nela.

Para repetir uma ação em cada item, não precisa de laço. O Loop Over Items serve para dividir em lotes.
