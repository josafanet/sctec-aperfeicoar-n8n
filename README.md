# Workflows n8n do Aperfeiçoar SCTEC

Aqui ficam os workflows que usamos nas aulas de n8n do Aperfeiçoar SCTEC no SENAI. As pastas seguem a mesma organização do n8n da aula, então cada exemplo está no lugar em que vocês viram na tela

Na pasta AULAS estão os exemplos de cada encontro. Na pasta PROJETO fica o projeto da Orbita Labs, que vai crescendo ao longo do curso

## Mapas visuais das aulas

Escolha uma aula para ver o mapa. No celular, toque em **Ampliar a imagem** para ler os detalhes.

<details open>
<summary><strong>Aula 01 · Como a página confirma um pedido?</strong></summary>

![O formulário envia o nome de Marina. Três nós recebem o pedido, separam o nome e devolvem a confirmação à página.](AULAS/AULA%2001/aula-01-mapa-mental.png)

[Ampliar a imagem](AULAS/AULA%2001/aula-01-mapa-mental.png?raw=true) · [Abrir o SVG editável](AULAS/AULA%2001/aula-01-mapa-mental.svg) · [Ver os workflows da aula](AULAS/AULA%2001)

</details>

<details>
<summary><strong>Aula 02 · Como um pedido vira uma linha na tabela?</strong></summary>

![O fluxo organiza os campos do formulário, padroniza o nome e o WhatsApp e grava o contato na tabela de leads.](AULAS/AULA%2002/aula-02-mapa-mental.png)

[Ampliar a imagem](AULAS/AULA%2002/aula-02-mapa-mental.png?raw=true) · [Abrir o SVG editável](AULAS/AULA%2002/aula-02-mapa-mental.svg) · [Ver os workflows da aula](AULAS/AULA%2002)

</details>

<details>
<summary><strong>Aula 03 · Como o comercial fica sabendo do pedido?</strong></summary>

![Depois de gravar o contato, o fluxo reúne nome, e-mail e WhatsApp e envia esse resumo ao comercial pelo Slack.](AULAS/AULA%2003/aula-03-mapa-mental.png)

[Ampliar a imagem](AULAS/AULA%2003/aula-03-mapa-mental.png?raw=true) · [Abrir o SVG editável](AULAS/AULA%2003/aula-03-mapa-mental.svg) · [Ver os workflows da aula](AULAS/AULA%2003)

</details>

<details>
<summary><strong>Aula 04 · Como um pedido vira cartão?</strong></summary>

![Marina soma 95 pontos. O pedido vira um cartão com a etiqueta quente no Trello, e a tabela guarda o link para abri-lo. IF, Filter e Switch escolhem o caminho do pedido.](AULAS/AULA%2004/aula-04-mapa-mental.png)

[Ampliar a imagem](AULAS/AULA%2004/aula-04-mapa-mental.png?raw=true) · [Abrir o SVG editável](AULAS/AULA%2004/aula-04-mapa-mental.svg) · [Ver os workflows da aula](AULAS/AULA%2004)

</details>

<details>
<summary><strong>Aula 05 · O que a v5 faz com cada pedido?</strong></summary>

A aula 5 começa pelo que ficou da aula 4, como formulário, agendamento, HTTP Request, Loop e Google Sheets. Esses fluxos estão na pasta AULA 05

![A versão 5 valida o pedido, barra o robô, reconhece o pedido repetido e avisa quando o Trello falha. No rodapé, o que veio da aula 4.](AULAS/AULA%2005/aula-05-mapa-mental.png)

[Ampliar a imagem](AULAS/AULA%2005/aula-05-mapa-mental.png?raw=true) · [Abrir o SVG editável](AULAS/AULA%2005/aula-05-mapa-mental.svg) · [Ver os workflows da aula](AULAS/AULA%2005)

</details>

## Como importar no seu n8n

Abra a pasta do workflow, baixe o arquivo .json e, no seu n8n, crie um workflow novo. No menu de três pontinhos no canto superior direito escolha Import from File e selecione o arquivo

Se preferir, abra o .json aqui no GitHub, clique em Raw, copie tudo e cole direto no canvas vazio com Ctrl+V

O workflow chega desativado. Para testar use o botão Execute workflow e, quando quiser deixar o webhook funcionando de verdade, publique no seu n8n

## Estrutura

```
AULAS/
  AULA 01/
  AULA 02/
  AULA 03/
  AULA 04/
  AULA 05/
PROJETO/
  Orbita Labs v1/
  Orbita Labs v1 teste/
  Orbita Labs v2/
  Orbita Labs v3/
```

Cada pasta tem o arquivo do workflow e um README contando o que ele faz e como testar. Dentro do próprio workflow tem uma nota com o mesmo resumo, para quem preferir ler direto no canvas

Conforme as aulas avançarem, novas pastas vão aparecendo aqui
