# ADR-003 - Modelo de Economia e Progressao

- Status: Aceito

## Contexto
O jogo depende de uma economia clara, legível e escalável para sustentar sessões curtas, progressão contínua e monetização ética em modelo F2P. O modelo precisa evitar pay to win e permitir balanceamento remoto futuro.

## Decisao
Adotar economia dual:

- `Coins` como moeda principal obtida no loop operacional.
- `Gems` como moeda premium obtida por eventos, missões, login, rewarded ads e IAP.

Princípios:

- Toda progressão essencial deve ser alcançável com `Coins` e tempo.
- `Gems` aceleram, mas não bloqueiam progressão nuclear.
- Custos e recompensas virão de configurações de balanceamento externas via Scriptable Objects.
- Receita offline terá teto temporal e coeficientes conservadores.

## Consequencias
Consequências positivas:

- Clareza para jogador e time de design.
- Facilidade para criar sinks e faucets previsíveis.
- Base sólida para tuning de retenção e monetização.

Consequências negativas:

- Requer telemetria para evitar inflação de `Coins`.
- Curva de progressão precisa ser continuamente calibrada.
- Gems gratuitas precisam ser distribuídas com controle para não colapsar conversão.

## Alternativas Consideradas
- Economia de moeda única.
  - Rejeitada por reduzir espaço de monetização e pacing.
- Energia como bloqueio central de sessão.
  - Rejeitada por conflitar com fantasia de tycoon fluido.
- Premium currency dominante sobre todos os upgrades.
  - Rejeitada por risco de pay to win.

## Relacoes
- Documento relacionado: [Economia](../GDD/Economia.md)
- Documento relacionado: [Progressao](../GDD/Progressao.md)
- Documento relacionado: [Monetizacao](../GDD/Monetizacao.md)# ADR-003 - Economia Dual Currency com Escalabilidade por Faixas

- Status: Aprovado
- Data: 2026-06-02

## Contexto
PET SHOP ADMIN depende de uma economia clara, com progressao previsivel, metas de curto e medio prazo e monetizacao nao agressiva. O jogo precisa sustentar upgrades, expansoes, contratacoes e acelerares opcionais sem comprometer o equilibrio F2P.

## Decisao
Adotar economia de dupla moeda:

- `Coins` como moeda principal de progressao regular.
- `Gems` como moeda premium para conveniencia, aceleracao e ofertas limitadas.

Diretrizes de balanceamento:

- Custos escalam por faixa de progressao e nao apenas por multiplicador linear fixo.
- Receita combina servicos, vendas, hotel pet e clinica veterinaria em fases posteriores.
- Gems nao compram poder exclusivo; compram velocidade, conveniencia e acesso adiantado limitado.
- Rewarded Ads concedem impulsos ou recompensas moderadas sem invalidar o ritmo base.

## Consequencias
Positivas:

- Facil compreensao para o jogador.
- Permite loops de motivacao de curto prazo com coins e metas de aspiracao com gems.
- Facil integracao com ofertas sazonais e live ops.
- Menor risco de pay to win em comparacao com power gating premium.

Negativas:

- Requer calibracao constante para evitar inflacao de coins em fases tardias.
- Exige cuidado para gems nao se tornarem irrelevantes ou excessivamente dominantes.
- Cria dependencia de tabelas de balanceamento por faixa, aumentando custo de tuning.

## Alternativas Consideradas
- Economia de moeda unica: descartada por limitar espaco de monetizacao e eventos.
- Multiplicadores agressivos exponenciais para tudo: descartado por dificultar previsibilidade de tuning.
- Power items exclusivos via IAP: descartado por contrariar posicionamento F2P justo.

## Relacoes
- Baseado em [Economia](../GDD/Economia.md)
- Relacionado com [Fluxo Economia](../Diagramas/Fluxo_Economia.md)
- Complementa [ADR-005 - Monetizacao](ADR-005-Monetizacao.md)