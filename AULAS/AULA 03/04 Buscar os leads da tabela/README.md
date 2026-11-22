# 04 Buscar os leads da tabela

Exemplo da aula 3 para ler o que já foi gravado na tabela.

## O que faz

Lê todas as linhas da tabela `leads` de uma vez. Cada linha vira um item no n8n. O último nó conta quantos itens chegaram.

## Como testar

Escolha a sua tabela no **Buscar Leads** e clique em **Execute workflow**. Compare o número de itens na saída com o número de linhas da tabela na aba **Data tables**. O **Contar os itens** mostra o total no campo `total`.

Use a mesma tabela `leads` da Orbita Labs v2. Se ainda não tiver, crie uma Data Table `leads` e mande alguns pedidos de teste.

## O que treinar

1. Mande mais um pedido pela página da Orbita e rode de novo. O total deve subir 1.
2. No **Buscar Leads**, desligue **Return All** e coloque 3 no limite. Veja quantos itens chegam.
3. Acrescente uma condição para trazer só quem tem `consentimento` igual a `sim`.

## Erros comuns

O nó fica vermelho quando a tabela ainda não foi escolhida.

Com a tabela vazia, o **Buscar Leads** não devolve itens e o fluxo para ali.
