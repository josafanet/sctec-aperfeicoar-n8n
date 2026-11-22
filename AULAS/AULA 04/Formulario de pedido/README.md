# Formulário de pedido

A Orbita recebe um pedido de diagnóstico por um formulário do n8n. Depois do envio, você vê o nome, o e-mail e a empresa no último nó.

## Como testar

Abra um workflow novo no n8n. No menu **⋯**, escolha **Import from File** e selecione [o JSON deste exemplo](aula-04-formulario-de-pedido.json).

1. Clique em **Execute workflow**. O n8n abre o formulário. Se a aba não abrir, copie a **Test URL** em **Receber formulário** e abra no navegador.
2. Use o nome `Ana de Teste`, o e-mail `ana@example.com` e a empresa `Oficina de Teste`. Envie e confira a mensagem de recebimento.
3. Volte ao editor e abra **Ver pedido → Output**. Procure os campos `nome`, `email` e `empresa`.

## O que treinar

Clique em **Execute workflow** outra vez e envie um pedido com a empresa em branco. O campo `empresa` deve aparecer vazio na saída.

## Erros comuns

- Se a Test URL expirou, inicie outra execução antes de enviar o formulário.
- Se apenas **Receber formulário** tiver saída, volte ao canvas e clique em **Execute workflow** para testar o percurso inteiro.

Consulte o [guia do formulário do n8n](https://docs.n8n.io/integrations/builtin/core-nodes/n8n-nodes-base.formtrigger/).
