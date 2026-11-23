# Validar quatro pedidos

Quatro pedidos fictícios passam pela mesma validação do captador v5. Nada é gravado e nenhuma credencial é pedida.

## Como testar

Importe [o JSON deste exemplo](aula-05-validar-quatro-pedidos.json) e clique em **Execute workflow**. Antes de abrir **Entrada válida?**, tente prever a saída de cada pedido.

| Pedido | Saída | Mensagem |
|---|---|---|
| Marina, completo | `valido` | vazia |
| Nome vazio | `invalido` | `Informe seu nome.` |
| E-mail `marina@grupovale` | `invalido` | `Confira o e-mail.` |
| Campo isca preenchido | `robo` | `Recebemos seu pedido.` |

O campo `site` é uma isca. A página da campanha esconde esse campo, então uma pessoa não preenche. Um robô preenche tudo. Quando ele vem preenchido, o captador responde como se estivesse tudo certo e não grava nada.

## O que treinar

Em **Quatro pedidos de teste**, apague o e-mail e o WhatsApp da Marina e execute. A mensagem passa a pedir um e-mail ou um WhatsApp.
