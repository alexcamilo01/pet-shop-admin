# Monetizacao

Este documento estabelece a estrategia de monetizacao do jogo, cobrindo anuncios, IAPs, guardrails de F2P justo e criterios para integracao comercial sem comprometer a experiencia.

## Ads
- Rewarded Ads: boost de receita, gems extras, acelerar cooldown.
- Interstitial Ads: exibicao controlada em pausas naturais (entre ciclos).

## IAP
- Remove Ads.
- Starter Pack.
- Gem Pack (S/M/L/XL).
- VIP Pack mensal.

## Equilibrio F2P
- Todo conteudo jogavel sem compra.
- IAP acelera conveniencia, nao poder bruto exclusivo.
- Limite de pressao de ads por sessao.

## Guardrails
- Max interstitial: 1 a cada 4 minutos de gameplay ativo.
- Rewarded sempre opt-in.
- Starter pack ofertado ate nivel 10.

## Responsabilidades
- Sustentar receita sem comprometer experiencia.
- Integrar ofertas ao contexto do jogador.

## Dependencias
- [Economia](Economia.md)
- [Idle System](Idle_System.md)
- [UI UX](UI_UX.md)

## Regras de Negocio
- Nenhuma compra desbloqueia vitoria automatica.
- Beneficios VIP devem ser transparentes e reversiveis no balance.

## Eventos
- `AdOfferShown`
- `RewardedCompleted`
- `IAPPurchased`
- `OfferConverted`

## Fluxo Operacional
1. Identificar momento de oferta.
2. Exibir opcao adequada ao contexto.
3. Processar confirmacao (ad/IAP).
4. Aplicar recompensa e registrar telemetria.
