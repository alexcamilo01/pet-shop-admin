# Gameplay

Este documento descreve a experiencia moment-to-moment do jogador, com foco em controle, acoes executaveis e regras que transformam interacao manual em progresso economico e operacional.

## Controle
- Joystick virtual (lado esquerdo).
- Camera terceira pessoa com angulo top-down inclinado.
- Interacao contextual por proximidade (auto-prompt).

## Acoes
### Banho
- Pegar shampoo no estoque.
- Levar animal para estacao de banho.
- Iniciar lavagem e aguardar tempo de execucao.

### Tosa
- Levar animal para estacao de tosa.
- Executar tosa com animacao de tarefa.
- Finalizar servico e enviar para entrega.

### Alimentacao
- Repor estoque de racao.
- Alimentar animais em espera/hotel.

### Limpeza
- Recolher sujeira gerada por animais e fluxo da loja.
- Higienizar area para manter bonus de satisfacao.

### Atendimento
- Receber clientes na recepcao.
- Entregar animal pronto para retirada.

## Regras de Controle
- Jogador pode carregar ate `carryCapacity` itens/animais.
- Interacao bloqueada quando estacao esta ocupada.
- Prioridade visual para tarefas com maior atraso de fila.

## Responsabilidades
- Definir experiencia moment-to-moment.
- Traduzir input em tarefas economicas validas.

## Dependencias
- [Game Loop](Game_Loop.md)
- [Estacoes](Estacoes.md)
- [Animais](Animais.md)
- [UI UX](UI_UX.md)

## Regras de Negocio
- Toda acao manual deve gerar impacto economico imediato ou preparar impacto futuro.
- Tempo de tarefa nunca pode ser zero; minimo 2s para legibilidade.

## Eventos
- `PlayerMoved`
- `InteractionStarted`
- `TaskCompleted`
- `QueueUpdated`

## Fluxo Operacional
1. Jogador se move ate ponto de tarefa.
2. Sistema valida pre-condicoes (estoque, estacao, fila).
3. Tarefa e executada.
4. Recompensas/estado sao aplicados.
5. UI atualiza progresso e prioridades.
