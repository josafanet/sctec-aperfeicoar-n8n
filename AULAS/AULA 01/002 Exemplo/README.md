# 002 Exemplo

Primeiro webhook da turma. Ele fica esperando uma chamada no caminho cadastro e passa tudo o que recebeu para o próximo nó

## O que tem no fluxo

O Webhook Boas Vindas escuta requisições GET em cadastro. Qualquer coisa que vier na URL, nos cabeçalhos ou no corpo chega no fluxo como dado

O Normalizar é um Edit Fields (Set) que ainda está sem campos. Ele está ali para você montar os seus campos a partir do que o webhook entregou

## Como testar

Importe o arquivo e clique em Execute workflow. O n8n fica aguardando a chamada. Abra o nó Webhook Boas Vindas, copie a Test URL e cole no navegador, se quiser acrescente algo como ?nome=Ana no fim do endereço

Volte para o n8n e veja os dados que chegaram. Depois tente criar no Normalizar um campo nome usando o valor que veio na URL
