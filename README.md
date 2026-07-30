# Voos VIX → REC / JPA — tracker de preços

Planilha viva + painel para acompanhar o preço de passagens aéreas de ida e volta de Vitória (VIX) para Recife (REC) ou João Pessoa (JPA), nas duas combinações de datas:

- Ida 03/09/2026 → volta 13/09/2026
- Ida 04/09/2026 → volta 14/09/2026

## Arquivos

- [`dados_voos.csv`](./dados_voos.csv) — planilha viva. Cada linha é uma opção de voo (ida e volta) encontrada em uma data de coleta, com companhia, horários da ida, duração, escalas e preço total.
- [`index.html`](./index.html) — painel: top 3 melhor custo-benefício (recalculado a partir dos dados), comparativo de preço por janela de datas e tabela completa de voos.

## Automação

Uma rotina na nuvem roda todo dia às 07h (horário de Brasília) e faz uma nova busca de preços para as duas combinações de ida e volta acima, adicionando linhas novas a `dados_voos.csv` com a data de coleta do dia. O painel recalcula o top 3 e o comparativo automaticamente a cada carregamento — nenhuma edição manual é necessária.

## Observações

- Preços são de tarifa base (1 adulto), incluem item pessoal + bagagem de mão conforme franquia padrão de cada companhia. Despacho de mala (se necessário) é cobrado à parte e não está refletido aqui.
- "Melhor custo-benefício" pondera preço, duração total e número de escalas — não é apenas o menor preço.
- O histórico de preço por dia de coleta (`data_coleta`) permite ver como o preço de cada combinação de ida/volta varia com o tempo, à medida que a rotina diária acrescenta novas linhas.
