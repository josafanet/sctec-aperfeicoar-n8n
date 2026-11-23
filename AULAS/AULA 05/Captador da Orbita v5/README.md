# Orbita Labs v5 · Captador da turma

A v5 é a v4 com quatro proteções antes do cartão.

- **Validar pedido** confere nome, e-mail, contato e autorização.
- **Entrada válida?** responde ao robô sem gravar e devolve 400 ao pedido incompleto.
- **Consultar cadastro** e **Já cadastrado?** impedem um segundo cartão para o mesmo e-mail ou WhatsApp.
- A saída de erro do Trello responde 502 e marca a execução como erro.

## Preparar sua cópia

1. Importe [o JSON do captador](aula-05-captador-v5.json) num workflow novo.
2. Em **Consultar cadastro** e em **Adicionar Lead**, escolha a sua tabela `leads`. Abra **Settings** do **Consultar cadastro** e confira **Always Output Data** ligado.
3. Em **Configurar Trello**, cole os quatro IDs do seu quadro, como na aula 4. Em **Criar cartão no Trello**, escolha a sua credencial.
4. Depois de importar o [Alerta de erro](../Alerta%20de%20erro/README.md), abra **Settings** deste workflow e escolha esse fluxo em **Error workflow**.

## O código da validação

Cole num nó **Code** chamado `Validar pedido`, em **Run Once for Each Item**, logo depois de **Normalizar Dados**.

```javascript
const d = $json;

// O campo site fica escondido na página. Uma pessoa não vê. Um robô preenche.
if (d.site) return { json: { ...d, rota: 'robo', mensagem: 'Recebemos seu pedido.' } };

const erros = [];
if (!d.nome) erros.push('Informe seu nome.');
if (d.email && !/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(d.email)) erros.push('Confira o e-mail.');
if (!d.email && !d.whatsapp) erros.push('Informe um e-mail ou um WhatsApp.');
if (d.consentimento !== 'sim') erros.push('Marque a autorização de contato.');

return { json: { ...d, rota: erros.length ? 'invalido' : 'valido', mensagem: erros.join(' ') } };
```

Para a isca chegar até aqui, acrescente o campo `site` em **Variáveis**, com `{{ $json.body?.site ?? '' }}`, e em **Normalizar Dados**, com `{{ ($json.site || '').trim() }}`.

## Testar

Cole a **Test URL**, que termina em `/orbita-v5`, no rodapé da [página da Orbita](https://orbita-automacao-gratuita.lovable.app/). Clique em **Execute workflow** antes de cada envio.

| Envio | Resposta | Cartão |
|---|---|---|
| Marina, com a autorização marcada | confirmação com o nome | um cartão novo |
| Nome vazio | 400 | nenhum |
| E-mail `marina@grupovale` | 400 | nenhum |
| Marina de novo | `Seu pedido já está com a nossa equipe` | continua um só |

A página mostra só "O fluxo respondeu 400." A mensagem do erro aparece na execução. Use uma tabela de treino vazia ou um e-mail novo, porque a tabela da aula 4 já tem a Marina.

### Testar a chamada

Clique em Execute workflow e use a Test URL, ou publique o fluxo e use a Production URL. Depois mande a chamada por uma destas ferramentas.

- [Postman](https://www.postman.com/downloads/)
- [Insomnia](https://insomnia.rest/download)
- [Thunder Client](https://marketplace.visualstudio.com/items?itemName=rangav.vscode-thunder-client), extensão do VS Code

## Se o teste parar

- **Um pedido novo fica sem resposta.** Ligue **Always Output Data** em **Settings** do **Consultar cadastro**.
- **Todo pedido cai em pedido repetido.** A tabela já tem esse e-mail, ou a condição da consulta ficou vazia.
- **Todo pedido recebe 400.** O campo `consentimento` ou o `site` não chega em **Normalizar Dados**, ou a autorização não foi marcada na página.
