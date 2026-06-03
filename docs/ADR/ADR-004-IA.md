# ADR-004 - IA de Funcionarios por State Machine

- Status: Aceito

## Contexto
Funcionários precisam operar de forma previsível, extensível e barata em CPU. A IA deve suportar tarefas repetitivas, priorização simples, retorno ao posto e pausas operacionais sem custo excessivo para mobile.

## Decisao
Adotar máquina de estados finitos para todos os funcionários com o núcleo:

- `Idle`
- `MoveToTask`
- `ExecuteTask`
- `Return`
- `Break`

Cada função especializada utiliza o mesmo esqueleto de estados, alterando apenas critérios de seleção de tarefa, tempos e animações. A seleção de trabalho será orientada por fila de tarefas publicada pelos services das estações.

## Consequencias
Consequências positivas:

- IA barata e previsível para mobile.
- Reuso de comportamento entre papéis.
- Debug mais simples em QA e analytics.

Consequências negativas:

- Menor sofisticação emergente que behavior trees.
- Escalonamento de prioridades complexas pode exigir camada extra.
- Estados mal definidos podem gerar lock se eventos falharem.

## Alternativas Consideradas
- Behavior Tree.
  - Rejeitada para MVP por custo de manutenção superior ao ganho real.
- GOAP.
  - Rejeitada por complexidade excessiva para o tipo de tarefa.
- Lógica procedural específica por funcionário.
  - Rejeitada por duplicação e alto custo de manutenção.

## Relacoes
- Documento relacionado: [IA](../GDD/IA.md)
- Documento relacionado: [Funcionarios](../GDD/Funcionarios.md)
- Documento relacionado: [Estacoes](../GDD/Estacoes.md)# ADR-004 - IA de Funcionarios Baseada em State Machine

- Status: Aprovado
- Data: 2026-06-02

## Contexto
O jogo depende de funcionarios autonomos para sustentar o fantasy de idle management. A IA precisa ser previsivel, barata computacionalmente, facil de depurar e extensivel conforme novas estacoes e papeis forem adicionados.

## Decisao
Adotar State Machine classica por funcionario com os estados base:

- `Idle`
- `MoveToTask`
- `ExecuteTask`
- `Return`
- `Break`

Diretrizes de implementacao:

- Cada role possui seletor de tarefas por prioridade e compatibilidade.
- Estados executam validacoes curtas e delegam regras de negocio ao dominio/servicos.
- Navegacao utiliza NavMesh ou solucao equivalente simples no escopo do projeto.
- Time slicing e intervalos de avaliacao reduzem custo de CPU em picos.

## Consequencias
Positivas:

- Modelo facil de entender por design, programacao e QA.
- Boa cobertura para o tipo de automacao esperado no genero.
- Depuracao objetiva com logs de transicao e gizmos de tarefa.
- Baixo custo de manutencao no MVP.

Negativas:

- Menor expressividade do que behavior trees em comportamentos complexos.
- Risco de proliferacao de condicoes especiais se as prioridades forem mal definidas.
- Necessita boa separacao entre logica de estado e logica de escolha de tarefa.

## Alternativas Consideradas
- Behavior Tree: descartada no MVP por overhead estrutural desnecessario.
- Utility AI completa: descartada por complexidade superior ao ganho inicial.
- Coroutines ad hoc sem maquina de estados: descartada por baixa previsibilidade e manutencao ruim.

## Relacoes
- Baseado em [IA](../GDD/IA.md)
- Relacionado com [Fluxo IA](../Diagramas/Fluxo_IA.md)
- Complementa [Funcionarios](../GDD/Funcionarios.md)