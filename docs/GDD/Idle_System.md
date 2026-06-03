# Idle System

Este documento descreve como a simulacao continua gerando valor com pouca ou nenhuma intervencao do jogador, cobrindo automacao, receita offline e limites de balanceamento do sistema idle.

## Objetivo
Permitir operacao e receita continua com funcionarios ativos, mesmo sem intervencao direta do jogador.

## Formula Base de Receita Idle
- Receita por tick: `R_tick = sum((throughput_estacao * ticket_medio) * eficiencia_global)`
- Receita offline: `R_offline = R_tick * ticksValidos * limiteOffline`
- Limite offline MVP: 4 horas.

## Regras de Balanceamento
- Efetividade offline: 65% da receita online para manter valor de sessao ativa.
- Cap por coleta offline para evitar inflacao explosiva.
- Boost de ads aplica multiplicador temporario sem quebrar economia.

## Responsabilidades
- Sustentar progressao em janelas curtas de jogo.
- Recompensar retorno diario do jogador.

## Dependencias
- [Economia](Economia.md)
- [Funcionarios](Funcionarios.md)
- [Save System](Save_System.md)

## Regras de Negocio
- So tarefas automativeis geram idle.
- Gargalo de estoque reduz throughput idle automaticamente.

## Eventos
- `IdleTick`
- `OfflineEarningsCalculated`
- `OfflineEarningsClaimed`

## Fluxo Operacional
1. Simular throughput por estacao ativa.
2. Aplicar multiplicadores e caps.
3. Registrar ganho em buffer de recompensa.
4. Entregar recompensa no login/retorno.
