# Quando o CRM falha

O nó **Criar cartão no CRM (simulado)** chama um endereço de teste que sempre responde 503, como um CRM fora do ar. Nenhuma credencial é pedida.

## Como testar

Importe [o JSON deste exemplo](aula-05-quando-o-crm-falha.json).

1. Clique em **Execute workflow**. O pedido sai pela saída de erro e **Parar e avisar** fica vermelho.
2. Abra **Executions** e encontre esta execução com o status **Error**.
3. Abra **Montar registro da falha** e leia `quando`, `etapa` e `mensagem`.
4. No nó do CRM, troque o fim do endereço de `503` para `200` e execute. O pedido sai por **Cartão criado**.

## Por que não repetir sozinho

Em **Settings** do nó, **On Error** está em **Continue (using error output)**. Ele ganha uma saída só para a falha. A opção **Retry On Fail** tentaria de novo, mas, se o CRM criou o cartão e só a resposta se perdeu, nasceria um cartão repetido. Por isso o fluxo para e uma pessoa confere o quadro antes de reenviar.
