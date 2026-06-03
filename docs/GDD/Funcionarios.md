# Funcionarios

Este documento especifica os papeis operacionais dos funcionarios, suas responsabilidades, atributos base, estados de IA e impacto direto na automacao do pet shop.

## Tabela de Cargos
| Cargo | Responsabilidades | IA Prioritaria | Velocidade Base | Eficiencia Base | Upgrades Principais |
|---|---|---|---:|---:|---|
| Recepcionista | Check-in, fila, entrega | Recepcao > Caixa | 1.0 | 1.0 | Atalho de fila, multiticket |
| Banhista | Banho e secagem | Banho > Secagem | 0.95 | 1.1 | Banho rapido, consumo menor |
| Tosador | Servico de tosa | Tosa | 0.9 | 1.2 | Corte premium, bonus de qualidade |
| Faxineiro | Limpeza e higiene | Sujeira critica > rota | 1.1 | 1.0 | Rota otimizada, area ampliada |
| Alimentador | Reposicao e alimentacao | Estoque baixo > alimentar | 1.0 | 1.0 | Capacidade de carga, velocidade |
| Gerente | Automacao e boost | Balancear gargalos | 1.05 | 1.3 | Auto-priorizacao, buff global |
| Veterinario | Tratamento premium | Vet queue | 0.85 | 1.5 | Diagnostico rapido, ticket alto |

## Estados da IA de Funcionario
- `Idle`
- `MoveToTask`
- `ExecuteTask`
- `Return`
- `Break`

## Responsabilidades
- Automatizar tarefas repetitivas.
- Manter throughput da loja.

## Dependencias
- [IA](IA.md)
- [Estacoes](Estacoes.md)
- [Idle System](Idle_System.md)

## Regras de Negocio
- Break ocorre por stamina/intervalo de turno.
- Gerente nunca substitui papel especialista; apenas acelera.

## Eventos
- `EmployeeHired`
- `EmployeeAssigned`
- `EmployeeStateChanged`
- `EmployeeUpgraded`

## Fluxo Operacional
1. Scheduler cria lista de tarefas.
2. Funcionario seleciona tarefa por prioridade.
3. Executa trabalho na estacao.
4. Retorna ao ponto base ou proxima tarefa.
