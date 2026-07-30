# Voos VIX → REC / JPA — tracker de preços

Planilha viva + painel para acompanhar o preço de passagens aéreas de Vitória (VIX) para Recife (REC) ou João Pessoa (JPA), nas janelas de datas:

- 04/09/2026 a 12/09/2026
- 03/09/2026 a 13/09/2026

## Arquivos

- [`dados_voos.csv`](./dados_voos.csv) — planilha viva. Cada linha é um voo encontrado em uma data de coleta, com companhia, horários, duração, escalas e preço de ida.
- [`index.html`](./index.html) — painel: top 3 melhor custo-benefício (recalculado a partir dos dados), valor diário por rota e tabela completa de voos.

## Automação

Uma rotina na nuvem roda todo dia às 07h (horário de Brasília) e faz uma nova busca de preços para as datas dentro das duas janelas acima, adicionando linhas novas a `dados_voos.csv` com a data de coleta do dia. O painel recalcula o top 3 e o comparativo automaticamente a cada carregamento — nenhuma edição manual é necessária.

## Observações

- Preços são de tarifa base (1 adulto), incluem item pessoal + bagagem de mão conforme franquia padrão de cada companhia. Despacho de mala (se necessário) é cobrado à parte e não está refletido aqui.
- "Melhor custo-benefício" pondera preço, duração total e número de escalas — não é apenas o menor preço.
- Cobertura de datas é incremental: nem todos os dias das janelas têm dado no início — a rotina diária vai completando ao longo dos dias.
