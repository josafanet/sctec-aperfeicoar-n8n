# Captador de Lead

Exemplo da aula 2 para entender os erros mais comuns quando a página chama o webhook

## O que tem no fluxo

O Gatilho da Pagina Orbita recebe um POST no caminho captador-lead. O Respond dele ficou no padrão, que responde na hora com Workflow was started

O Responder a chamada devolve o texto AGORA FOI, mas está solto no canvas, sem ligação com o gatilho

## O que treinar

Do jeito que está, a página recebe Workflow was started e nunca o AGORA FOI. Para ver a resposta personalizada, ligue o Responder a chamada depois do gatilho e troque o Respond do gatilho para Using Respond to Webhook Node

Faça também o caminho contrário. Deixe o Respond em Using Respond to Webhook Node e desligue o Responder a chamada. A página recebe erro 500, e na execução o n8n avisa que não achou o nó de resposta

## Como testar

Clique em Execute workflow, copie a Test URL e mande um POST

```bash
curl -X POST "COLE_A_TEST_URL_AQUI" -d "nome=Joca"
```

Depois publique o workflow e repita com a Production URL. A execução não aparece no canvas, só na aba Executions
