# Aula 5 · Integrar, validar e publicar

A aula começa pelo que ficou da aula 4, que são o formulário, o agendamento, o HTTP Request com credencial, o Loop e o Google Sheets. Depois, o captador da Orbita fica pronto para produção. Ele confere o pedido antes de gravar, barra o robô, não cria um cartão repetido e avisa quando o Trello falha.

## Primeiro, o que ficou da aula 4

Estes exemplos estão na pasta da aula 4.

| O que você quer fazer? | Por onde começar |
|---|---|
| Receber um pedido pelo formulário do próprio n8n | [Formulário de pedido](../AULA%2004/Formulario%20de%20pedido/README.md) |
| Contar os pedidos que chegaram no dia anterior | [Resumo diário de leads](../AULA%2004/Resumo%20diario%20de%20leads/README.md) |
| Fazer a primeira consulta HTTP, sem credencial | [Consultar feriados](../AULA%2004/Consultar%20feriados/README.md) |
| Descobrir onde informar o usuário e a senha de uma API | [HTTP com Basic Auth](../AULA%2004/HTTP%20com%20Basic%20Auth/README.md) |
| Descobrir onde informar o token de uma API | [HTTP com Bearer](../AULA%2004/HTTP%20com%20Bearer/README.md) |
| Dividir os itens em lotes com o Loop Over Items | [Loop · Processar em lotes](../AULA%2004/CONCEITOS/Loop%20Processar%20em%20lotes/README.md) |
| Acrescentar um pedido à aba `Pedidos` da planilha | [Gravar no Google Sheets](../AULA%2004/Gravar%20no%20Google%20Sheets/README.md) |
| Receber no n8n a próxima linha acrescentada nessa aba | [Receber nova linha do Google Sheets](../AULA%2004/Receber%20nova%20linha%20do%20Google%20Sheets/README.md) |
| Montar o mesmo quadro no Notion | [Modelos de CRM](../AULA%2004/Modelos%20de%20CRM/README.md) |

## Depois, o captador pronto para produção

| O que você quer fazer? | Por onde começar |
|---|---|
| Achar o erro de um fluxo pela execução | [Depurar um pedido](Depurar%20um%20pedido/README.md) |
| Ver a validação funcionando sem gravar nada | [Validar quatro pedidos](Validar%20quatro%20pedidos/README.md) |
| Montar ou conferir o captador da versão 5 | [Captador da Orbita v5](Captador%20da%20Orbita%20v5/README.md) |
| Mandar os pedidos de teste de uma vez e guardar a evidência | [Enviar os pedidos de teste](Enviar%20os%20pedidos%20de%20teste/README.md) |
| Ver o que acontece quando o CRM sai do ar | [Quando o CRM falha](Quando%20o%20CRM%20falha/README.md) |
| Guardar as falhas dos fluxos publicados numa tabela | [Alerta de erro](Alerta%20de%20erro/README.md) |

## Para a aula 6 (26/11/2026)

Estes dois exemplos ficam nesta pasta, mas são vistos na aula 6.

| O que você quer fazer? | Por onde começar |
|---|---|
| Separar uma consulta num fluxo que outro chama | [Subfluxo de leads](Subfluxo%20de%20leads/README.md) |
| Conversar com um agente que consulta os leads | [Agente de IA](Agente%20de%20IA/README.md) |

Para cada exemplo, baixe o JSON pelo botão **Download raw file** do GitHub. Abra um workflow vazio no n8n e, no menu **⋯**, escolha **Import from File**. A nota **Leia primeiro** no próprio fluxo e o README da pasta mostram o que preencher e como reconhecer o resultado. Use só dados fictícios nos testes.
