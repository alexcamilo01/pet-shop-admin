# Conquistas

Este documento define o sistema de conquistas permanentes do produto, incluindo marcos, criterios de desbloqueio e sua funcao no engajamento de medio e longo prazo.

## Sistema
Conquistas permanentes por marcos de desempenho, volume e eficiencia.

## Lista Inicial
| Categoria | Conquista | Criterio | Recompensa |
|---|---|---|---|
| Operacao | Primeiro Dia de Loja | Concluir 1 ciclo completo | 100 Coins |
| Atendimento | Cliente Feliz | 50 entregas sem atraso | 10 Gems |
| Expansao | Empreendedor | Desbloquear Fase 3 | 500 Coins |
| Automacao | Time Completo | Contratar 5 funcionarios | 20 Gems |
| Premium | Clinica Ativa | Desbloquear Veterinario | Skin de uniforme |

## Responsabilidades
- Reforcar sensacao de progresso longo.
- Gerar metas paralelas ao loop principal.

## Dependencias
- [Missoes](Missoes.md)
- [Progressao](Progressao.md)
- [UI UX](UI_UX.md)

## Regras de Negocio
- Conquistas nao expiram.
- Recompensa deve ser dada uma unica vez.

## Eventos
- `AchievementUnlocked`
- `AchievementClaimed`

## Fluxo Operacional
1. Monitorar counters globais.
2. Validar threshold.
3. Desbloquear conquista.
4. Exibir feedback e permitir claim.
