# Orbita Labs v2

Segunda versão do projeto da Orbita Labs, montada na aula 2. Agora a página manda o formulário completo e cada pedido fica guardado numa tabela dentro do próprio n8n

## O que tem no fluxo

O Disparo de Gatilho recebe o pedido por POST no caminho orbita-v2. O Respond dele está em Using Respond to Webhook Node, então a resposta sai pelo último nó

O Variaveis pega cada campo de dentro do body e deixa todos soltos, sem o body na frente. São nome, email, whatsapp, empresa, porte, area, prazo e consentimento, todos como String. O faturamento está como Number só para treinar a conversão de tipo, porque a página não manda esse campo

O Normalizar Dados arruma dois campos e repassa o resto como chegou

```
{{ $json.nome.toLowerCase().toTitleCase() }}
{{ $json.whatsapp.replace(/\D/g, '') }}
```

A primeira deixa tudo em minúsculas e depois coloca maiúscula na primeira letra de cada palavra, então MARIA borges vira Maria Borges. A segunda usa uma expressão regular que apaga tudo o que não é número, então (67) 99272-0990 vira 67992720990

O Adicionar Lead é um nó Data Table que insere uma linha na tabela leads, com cada campo ligado à sua coluna

O Resposta do Gatilho devolve Recebemos seu pedido com o nome da pessoa

## Antes de testar

Crie no seu n8n uma Data Table chamada leads com as colunas nome, email, whatsapp, empresa, porte, area, prazo e consentimento. Depois abra o Adicionar Lead e escolha a sua tabela, porque a que vem no arquivo é a do professor e não existe no seu n8n

## Como testar

Clique em Execute workflow e copie a Test URL do Disparo de Gatilho. Abra a página da campanha com ?webhook= e a sua Test URL no fim do endereço, preencha o formulário completo e envie

```
https://orbita-automacao-gratuita.lovable.app/?webhook=COLE_A_TEST_URL_AQUI
```

A página deve mostrar Recebemos seu pedido com o nome arrumado, e a tabela leads ganha uma linha nova. Se quiser testar sem a página, mande um POST pelo terminal

```bash
curl -X POST "COLE_A_TEST_URL_AQUI" -d "nome=MARIA borges" -d "whatsapp=(67) 99272-0990" -d "email=maria@exemplo.com"
```

Na aula 3 este fluxo ganha o trim, o e-mail em minúsculas e um IF para responder de um jeito para quem deixou e-mail e de outro para quem não deixou
