# Missoes

Este documento especifica o sistema de missoes como ferramenta de retencao, orientacao de comportamento e distribuicao de recompensas de curto e medio prazo.

## Estrutura
- Missoes Diarias: reset a cada 24h.
- Missoes Semanais: reset semanal com recompensas maiores.
- Eventos Temporarios: janela limitada com objetivos especiais.

## Exemplos de Missoes
| Tipo | Objetivo | Recompensa |
|---|---|---|
| Diaria | Concluir 12 servicos de banho | 300 Coins + 5 Gems |
| Diaria | Vender 8 itens na loja | 250 Coins |
| Semanal | Contratar 2 funcionarios | 1,500 Coins + 30 Gems |
| Evento | Atender 20 pets exoticos | Item cosmetico + 40 Gems |

## Responsabilidades
- Aumentar recorrencia de sessao.
- Direcionar comportamento para loops chave.

## Dependencias
- [Economia](Economia.md)
- [Progressao](Progressao.md)
- [UI UX](UI_UX.md)

## Regras de Negocio
- Sempre mostrar no minimo 3 missoes diarias.
- Recompensa deve refletir tempo estimado da tarefa.

## Eventos
- `MissionAssigned`
- `MissionProgressed`
- `MissionCompleted`
- `MissionReset`

## Fluxo Operacional
1. Gerar conjunto de missoes por perfil de progresso.
2. Atualizar progresso por evento de gameplay.
3. Entregar recompensa ao claim.
4. Registrar analytics de conclusao.
