# 001 Exemplo

Primeiro contato com dados dentro do n8n. O fluxo recebe um objeto aluno com nome e sobrenome e monta um campo novo chamado nomecompleto no formato sobrenome, nome

## O que tem no fluxo

O Gatilho Manual inicia tudo quando você clica em Execute workflow. Ele já vem com dados fixados (pin data), então não precisa digitar nada para testar

O Normalizar Dados é um nó Edit Fields (Set) que cria o campo nomecompleto juntando os dois valores com a expressão abaixo

```
{{ $json.aluno.sobrenome }}, {{ $json.aluno.nome }}
```

## Como testar

Importe o arquivo, clique em Execute workflow e abra o nó Normalizar Dados. Na saída vai aparecer o nome completo montado a partir dos dados de exemplo

Para praticar, troque o nome e o sobrenome nos dados fixados do gatilho e veja o resultado mudar sem mexer na expressão
