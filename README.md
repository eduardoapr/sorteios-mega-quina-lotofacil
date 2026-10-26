# Sorteios da Mega-Sena, da Quina e da Lotofácil

**English summary.** Draw history of three Brazilian lotteries run by Caixa Econômica Federal (Mega-Sena, Quina and Lotofácil), one row per draw: the numbers drawn, the number of top-prize winners and a flag for draws whose numbers all fall between 1 and 31, the range of calendar dates. Snapshot of 2026-10-26. Compiled by mundodasloterias.com.br, an independent site with no link to Caixa. The data backs a study showing that when every number drawn is 31 or lower, more people share the top prize. It does not change anyone's odds: every combination is equally likely in every draw, and picking numbers above 31 only lowers the chance of sharing a prize, never the chance of winning one. Study (in Portuguese): https://mundodasloterias.com.br/estudos/datas-de-aniversario-e-divisao-de-premio/. License: CC BY 4.0 for the computed columns and the file layout; the draw results are published by Caixa under its own terms of use.

## O que é

O histórico completo de sorteios de três loterias da Caixa, uma linha por concurso e um arquivo por jogo. É um retrato da base em 2026-10-26; a versão atualizada a cada concurso está no site:

- https://mundodasloterias.com.br/dados/sorteios-megasena.csv
- https://mundodasloterias.com.br/dados/sorteios-quina.csv
- https://mundodasloterias.com.br/dados/sorteios-lotofacil.csv

Os arquivos do site começam com 4 linhas de comentário (iniciadas por `#`), que alguns leitores de CSV não aceitam; os deste repositório não têm essas linhas e abrem direto.

## Arquivos

| Arquivo | Concursos | Período |
|---|---|---|
| `sorteios-megasena.csv` | 1 a 3074 | 11/03/1996 a 24/10/2026 |
| `sorteios-quina.csv` | 1 a 7151 | 13/03/1994 a 24/10/2026 |
| `sorteios-lotofacil.csv` | 1 a 3813 | 29/09/2003 a 24/10/2026 |

Na Quina, o concurso 380 aparece com data 12/03/1997, como a Caixa publica; pela sequência (379 em 08/03/1998, 381 em 15/03/1998), a data provável é 12/03/1998. O arquivo mantém a data publicada.

UTF-8, vírgula como separador, cabeçalho na primeira linha, sem aspas.

## Colunas

- `concurso`: número do concurso.
- `data`: data do sorteio, no formato AAAA-MM-DD.
- `dezenas`: as dezenas sorteadas em ordem crescente, com dois dígitos e separadas por espaço (6 na Mega-Sena, 5 na Quina, 15 na Lotofácil).
- `maior_dezena`: a maior dezena do sorteio (calculada).
- `todas_ate_31`: 1 quando todas as dezenas do sorteio são 31 ou menos, a faixa das datas de aniversário; 0 nos demais (calculada). Na Lotofácil, cujas dezenas vão de 1 a 25, vale sempre 1 e está ali só para os três arquivos terem as mesmas colunas.
- `ganhadores_faixa_principal`: número de apostas ganhadoras da faixa principal (sena na Mega-Sena, quina na Quina, 15 acertos na Lotofácil), como a Caixa publica.

## Fonte

Resultados oficiais publicados pela Caixa Econômica Federal (https://loterias.caixa.gov.br/). As colunas `maior_dezena` e `todas_ate_31` são calculadas pelo Mundo das Loterias. Este repositório não tem vínculo com a Caixa e não vende apostas.

## Para que serve, e o que estes dados não dizem

Estes arquivos bastam para refazer o estudo [Datas de aniversário e divisão de prêmio](https://mundodasloterias.com.br/estudos/datas-de-aniversario-e-divisao-de-premio/): quando o sorteio cai todo até 31, mais gente divide o prêmio, na Mega-Sena e na Quina. Na Quina, em 2026-10-26, esses sorteios tiveram em média 3,65 ganhadores, contra 0,77 nos demais. O estudo também aplica o mesmo teste a outra crença popular, repetir 9 dezenas do concurso anterior na Lotofácil, para mostrar que o método não acha efeito onde não há; isso se calcula pelas `dezenas` de concursos consecutivos.

O efeito é sobre dividir o prêmio, nunca sobre ganhar. Cada sorteio é independente e todas as combinações têm a mesma probabilidade: jogar dezenas acima de 31 não aumenta a chance de ganhar; só reduz a chance de dividir o prêmio, se ele vier. Nada nestes dados ajuda a escolher dezenas que saiam mais.

## Licença

As colunas calculadas (`maior_dezena` e `todas_ate_31`) e a organização destes arquivos estão sob a licença [Creative Commons Atribuição 4.0 Internacional (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/deed.pt-br): pode copiar, adaptar e usar, inclusive para fins comerciais, desde que cite a fonte. Os resultados dos sorteios (`concurso`, `data`, `dezenas` e `ganhadores_faixa_principal`) são publicados pela Caixa Econômica Federal, que tem os próprios [termos de uso](https://www.caixa.gov.br/termos-de-uso/Paginas/default.aspx); a licença deste repositório não se estende a eles.

## Como citar

> Mundo das Loterias. *Sorteios da Mega-Sena, da Quina e da Lotofácil*, retrato de 2026-10-26. Disponível em https://github.com/eduardoapr/sorteios-mega-quina-lotofacil.
