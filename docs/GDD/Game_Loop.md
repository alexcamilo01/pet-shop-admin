# Game Loop Principal

Este documento formaliza o ciclo principal de valor do jogo, conectando atendimento, execucao de servicos, pagamento, reinvestimento e expansao da loja em um fluxo repetivel e escalavel.

## Fluxo Detalhado
1. Cliente chega a recepcao.
2. Cliente entrega animal.
3. Animal entra na fila por tipo de servico.
4. Jogador ou funcionario move animal para estacao.
5. Servico e executado (banho/tosa/secagem/alimentacao/vet).
6. Animal pronto retorna a area de retirada.
7. Cliente recebe animal.
8. Cliente paga no caixa.
9. Receita aumenta e desbloqueia upgrades.
10. Loja cresce por novas estacoes e contratacoes.

## Fluxograma Textual
Entrada Cliente -> Registro Recepcao -> Fila de Servico -> Alocacao de Recurso -> Execucao -> Entrega -> Pagamento -> Reinversao -> Expansao -> Novo Ciclo

## Estados Envolvidos
- Cliente: `Arriving`, `Waiting`, `Served`, `Paying`, `Leaving`
- Animal: `Queued`, `InService`, `Ready`, `Delivered`
- Estacao: `Locked`, `Idle`, `Busy`, `Maintenance`
- Funcionario: `Idle`, `MoveToTask`, `ExecuteTask`, `Return`, `Break`

## Eventos Envolvidos
- `CustomerArrived`
- `PetCheckedIn`
- `PetAssignedToStation`
- `ServiceStarted`
- `ServiceCompleted`
- `PaymentCompleted`
- `UpgradePurchased`
- `ExpansionUnlocked`

## Dependencias
- [Economia](Economia.md)
- [Funcionarios](Funcionarios.md)
- [IA](IA.md)
- [Expansao](Expansao.md)

## Responsabilidades
- Orquestrar ciclo principal de valor do jogo.
- Conectar systems de fila, servico e recompensa.

## Regras de Negocio
- Um animal so pode estar em uma etapa por vez.
- Pagamento ocorre apenas apos entrega concluida.
- Atraso acima de threshold reduz gorjeta.

## Fluxo Operacional
1. Spawn de cliente por taxa dinamica.
2. Check-in e classificacao do servico.
3. Scheduler define executor (player/NPC).
4. Execucao e atualizacao de fila.
5. Pagamento, analytics e progresso.
