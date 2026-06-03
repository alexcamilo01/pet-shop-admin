# Arvore de Upgrades

Este documento organiza a arvore de upgrades do jogo, detalhando atributos melhoraveis, curvas de custo, efeitos por nivel e sua funcao no aumento de throughput e rentabilidade.

## Tabela de Upgrades Principais
| Upgrade | Nivel Max | Efeito por Nivel | Custo Inicial (Coins) | Fator de Custo |
|---|---:|---|---:|---:|
| Velocidade do jogador | 20 | +4% move speed | 120 | 1.20 |
| Capacidade de transporte | 15 | +1 slot a cada 3 niveis | 150 | 1.22 |
| Velocidade de banho | 25 | -3% tempo banho | 180 | 1.19 |
| Velocidade de tosa | 25 | -3% tempo tosa | 200 | 1.19 |
| Capacidade de estoque | 20 | +6% estoque | 170 | 1.18 |
| Velocidade dos NPCs | 20 | +3% move speed NPC | 220 | 1.20 |
| Quantidade de clientes | 30 | +2% spawn rate | 260 | 1.23 |
| Valor dos servicos | 30 | +2.5% ticket | 300 | 1.24 |
| Gerente automatico | 10 | +1 regra de automacao | 500 | 1.30 |

## Formula
`Custo(n) = C0 * (fator ^ (n-1))`

## Responsabilidades
- Oferecer progresso tangivel e metas de investimento.
- Reduzir friccao operacional em fases avancadas.

## Dependencias
- [Economia](Economia.md)
- [Progressao](Progressao.md)
- [UI UX](UI_UX.md)

## Regras de Negocio
- Upgrades de conveniencia nao removem necessidade de estrategia.
- Compra deve exibir ROI estimado na UI.

## Eventos
- `UpgradeOffered`
- `UpgradePurchased`
- `UpgradeEffectApplied`

## Fluxo Operacional
1. Jogador abre tela de upgrades.
2. Sistema calcula elegibilidade e ROI.
3. Compra e aplicada.
4. Metricas de impacto sao registradas.
