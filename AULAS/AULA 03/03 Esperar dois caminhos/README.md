# 03 Esperar dois caminhos

Exemplo da aula 3 para ver a ordem dos caminhos, o Wait e o Merge.

## O que faz

O gatilho abre dois caminhos. Um segue direto. O outro espera 5 segundos. O **Juntar os dois** só continua depois que os dois chegam.

## Como testar

Clique em **Execute workflow**. Veja o caminho rápido terminar antes do outro. Abra o **Juntar os dois** e compare o campo `hora` dos dois itens.

## O que treinar

1. No **Esperar 5 segundos**, troque 5 por 10 e rode de novo. Compare as horas.
2. Arraste o **Caminho rápido** para baixo do outro e rode. Veja qual caminho roda primeiro agora.
3. Apague a ligação entre o **Caminho com espera** e o **Juntar os dois**. Rode e veja o que o Merge recebe.

## Erros comuns

Os caminhos não rodam ao mesmo tempo. O n8n termina um caminho e depois começa o outro, de cima para baixo. A distância entre os nós não muda nada.

Uma espera longa deixa a execução parada. Ela aparece em **Executions** e continua quando a hora chega.
