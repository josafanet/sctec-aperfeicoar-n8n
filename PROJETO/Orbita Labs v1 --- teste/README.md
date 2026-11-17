# Orbita Labs v1 teste

Cópia da Orbita Labs v1 usada para experimentar mudanças sem mexer na versão original. Os nós e as expressões são os mesmos, muda só a posição no canvas

## Por que ter uma cópia

Quando o fluxo já está funcionando, é mais seguro testar ideias numa cópia. Se algo der errado, a versão original continua lá do jeito que estava

## Um cuidado importante

As duas versões usam o mesmo caminho senai-orbita-v1 no webhook. Por isso só uma delas pode ficar publicada por vez. Se for publicar a cópia, despublique a original antes, ou troque o caminho da cópia para algo como senai-orbita-v1-teste

## Como testar

O teste é igual ao da v1. Importe, clique em Execute workflow, copie a Test URL do Disparo de Gatilho e mande um POST com o campo nome no corpo. A explicação completa de cada nó está no README da pasta Orbita Labs v1
