# Switch 2 · Separar por faixa de número

O Switch comparando número, como a nota do lead. Roda sem credencial nenhuma.

## O que faz

Cinco alunos fictícios chegam com a média final. O Switch **Situação** compara o número. A partir de 7, aprovado. De 5 a 6,9, recuperação. Abaixo de 5, reprovado, pela saída **Fallback**.

| Aluno | Média | Situação esperada |
|---|---|---|
| Aline | 9 | Aprovado |
| Bruno | 7 | Aprovado |
| Clara | 6,5 | Recuperação |
| Diego | 5 | Recuperação |
| Elisa | 3 | Reprovado |

## Como testar

Clique em **Execute workflow**. Devem passar 2 alunos em **Aprovado**, 2 em **Recuperação** e 1 em **Reprovado**.

## O que treinar

1. Antes de rodar, diga por qual saída passam o Bruno, com 7, e o Diego, com 5.
2. Em **Options**, ligue **Send data to all matching outputs** e rode. A Aline e o Bruno saem por duas saídas, porque 9 e 7 também são maiores que 5. Desligue de novo.
3. Na primeira regra, troque o 7 por 9 e rode. O Bruno, com 7, passa para recuperação. Volte para 7.

## Erros comuns

A ordem das regras conta. O Switch para na primeira regra que der certo.

A média precisa ser número. `"7"`, entre aspas, é texto, e a comparação de número falha.

**is greater than or equal to** inclui o 7. **is greater than** deixa o 7 de fora.
