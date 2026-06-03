# ADR-005 - Estrategia de Monetizacao F2P

- Status: Aceito

## Contexto
PET SHOP ADMIN será lançado como jogo mobile casual F2P. A monetização precisa gerar receita sem comprometer retenção, pacing ou percepção de justiça. O jogo depende de loop satisfatório e expansão de longo prazo, o que torna a percepção de abuso publicitário especialmente sensível.

## Decisao
Adotar monetização híbrida leve com:

- Rewarded Ads opcionais para aceleração situacional.
- Interstitials controlados por contexto e frequência limitada.
- IAPs de conveniência e valor percebido.

Princípios:

- Nenhum conteúdo central será exclusivo de pagamento.
- Rewarded Ads devem conceder valor claro e imediato.
- Interstitials não interrompem ações críticas nem fechamento de loop.
- Pacotes pagos focam aceleração, remoção de fricção e cosmética futura.

## Consequencias
Consequências positivas:

- Monetização compatível com audiência casual.
- Menor risco de churn por frustração.
- Melhor alinhamento com não pay to win.

Consequências negativas:

- Receita por usuário depende de tuning fino de oferta.
- Interstitials precisam de extrema moderação para não danificar sessão.
- Requer integração cuidadosa com progressão e metas diárias.

## Alternativas Consideradas
- Somente IAP.
  - Rejeitada por reduzir monetização de não pagantes.
- Forte dependência de interstitials.
  - Rejeitada por piorar retenção.
- Boosters exclusivos pagos que afetam núcleo competitivo.
  - Rejeitada por violar princípio não pay to win.

## Relacoes
- Documento relacionado: [Monetizacao](../GDD/Monetizacao.md)
- Documento relacionado: [Economia](../GDD/Economia.md)
- Documento relacionado: [Missoes](../GDD/Missoes.md)# ADR-005 - Monetizacao Hibrida com Ads Recompensados e IAP de Conveniencia

- Status: Aprovado
- Data: 2026-06-02

## Contexto
O jogo sera lancado como mobile F2P e precisa monetizar sem quebrar o pacing do core loop nem comprometer retencao por frustracao. O publico do genero tolera ads recompensados e ofertas de conveniencia, mas rejeita intervencoes excessivas e paywalls agressivos.

## Decisao
Adotar monetizacao hibrida composta por:

- Rewarded Ads para boosts temporarios, gems moderadas, tickets de aceleracao e recompensas de login/evento.
- Interstitial Ads em pontos de baixa friccao e com frequencia limitada.
- IAP de conveniencia: `Remove Ads`, `Starter Pack`, `Gem Pack`, `VIP Pack`.

Guardrails de design:

- Nenhuma compra desbloqueia estacao exclusiva obrigatoria.
- Todo conteudo funcional principal pode ser alcancado via progressao F2P.
- Rewarded Ads devem ser opcionais e claramente comunicados.
- Interstitials devem respeitar cooldown, milestones e segmento do jogador.

## Consequencias
Positivas:

- Boa compatibilidade com o genero e expectativa do mercado.
- Mantem monetizacao distribuita entre ads e IAP.
- Preserva a percepcao de justica se os guardrails forem seguidos.
- Facil de otimizar por cohorts apos o soft launch.

Negativas:

- Requer instrumentacao analitica para controlar canibalizacao entre rewarded e IAP.
- Interstitial mal calibrado pode afetar retencao cedo.
- VIP mal dimensionado pode gerar sensacao de pressao por assinatura indireta.

## Alternativas Consideradas
- Somente ads: descartado por teto de monetizacao limitado.
- Somente IAP: descartado por incompatibilidade com comportamento amplo do publico casual F2P.
- Gating agressivo de progresso via premium: descartado por risco de churn e desalinhamento com o posicionamento do projeto.

## Relacoes
- Baseado em [Monetizacao](../GDD/Monetizacao.md)
- Complementa [Economia](../GDD/Economia.md)