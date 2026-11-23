# Depurar um pedido

O pedido da Marina deveria dar 95 pontos e a faixa **quente**. Este fluxo tem dois defeitos de propósito. Um deixa um nó vermelho. O outro não dá erro nenhum e entrega a nota errada.

## Como testar

Importe [o fluxo com defeitos](aula-05-depurar-pedido-QUEBRADO.json) num workflow novo.

1. Clique em **Execute workflow**. O nó **Montar resposta** fica vermelho. Leia a mensagem e corrija o que ela aponta.
2. Execute de novo. Agora não há erro, mas a nota é 55 e a faixa é **morno**.
3. Abra **Nota do lead** e compare o que entrou com o que você esperava. Corrija o dado na origem e execute outra vez.

Com os dois defeitos corrigidos, a resposta é `Recebemos seu pedido, Marina Souza! Nota 95, faixa quente.`

## Roteiro de correção

1. Qual nó falhou ou deu o resultado errado?
2. O que entrou nele?
3. O que eu esperava que entrasse?
4. Corrijo o nó ou o dado de origem?
5. Testo de novo com o **mesmo** pedido.

Se travar, abra [o gabarito](aula-05-depurar-pedido-gabarito.json). A nota dele explica os dois defeitos.
