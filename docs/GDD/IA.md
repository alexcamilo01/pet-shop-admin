# Sistema de IA (State Machine)

Este documento apresenta a arquitetura comportamental dos funcionarios autonomos, detalhando estados, transicoes, prioridades de tarefa e responsabilidades do sistema de IA.

## Modelo
State Machine hierarquica por papel, com camada comum de locomocao e execucao de tarefas.

## Estados
- `Idle`: aguardando job elegivel.
- `MoveToTask`: navegacao ate alvo.
- `ExecuteTask`: animacao + timer + aplicacao de efeito.
- `Return`: retorno a home position/estacao base.
- `Break`: pausa programada.

## Transicoes
- `Idle -> MoveToTask`: job disponivel.
- `MoveToTask -> ExecuteTask`: chegou ao destino e pre-condicoes validas.
- `ExecuteTask -> Return`: task concluida.
- `Return -> Idle`: sem nova task imediata.
- `Any -> Break`: fadiga/rotina de turno.
- `Break -> Idle`: recuperacao concluida.

## Dependencias Tecnicas
- NavMesh.
- Job Queue Service.
- Event Bus.
- Time Service.

## Responsabilidades
- Garantir comportamento previsivel e debuggavel.
- Escalar para multiplos NPCs sem explosao de custo.

## Dependencias
- [Arquitetura](Arquitetura.md)
- [Funcionarios](Funcionarios.md)
- [Game Loop](Game_Loop.md)

## Regras de Negocio
- Timeout de navegacao reencaminha job.
- Job falho retorna para fila com prioridade aumentada.
- NPC em break nao recebe task critica exceto emergencia configurada.

## Eventos
- `AIStateEntered`
- `AIStateExited`
- `TaskClaimed`
- `TaskFailed`
- `TaskRequeued`

## Fluxo Operacional
1. Worker consulta fila.
2. Seleciona job por peso e distancia.
3. Move ate estacao.
4. Executa task e publica resultado.
5. Volta ao estado de espera.
