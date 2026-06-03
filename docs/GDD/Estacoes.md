# Estacoes de Trabalho

Este documento descreve as estacoes que compoem a operacao do pet shop, com foco em entradas, saidas, dependencias, eventos e regras de negocio por ponto de servico.

## Matriz de Estacoes
| Estacao | Objetivo | Entradas | Saidas | Dependencias | Eventos | Regra de Negocio |
|---|---|---|---|---|---|---|
| Banho | Limpeza do pet | Animal, shampoo, operador | Animal limpo | Estoque, agua | `BathStarted`, `BathEnded` | Requer item de shampoo |
| Tosa | Cortar pelo | Animal, tosador | Animal tosado | Banho recomendado | `GroomStarted`, `GroomEnded` | Penalidade se feito sem banho em certas racas |
| Secagem | Finalizar banho | Animal molhado | Animal pronto | Banho concluido | `DryingStarted`, `DryingEnded` | Slot unico no MVP |
| Alimentacao | Suporte hotel/espera | Racao, animal | Animal alimentado | Estoque de racao | `FeedStarted`, `FeedEnded` | Cooldown por animal |
| Recepcao | Check-in/checkout | Cliente, animal | Ordem de servico | Fila, UI ticket | `CheckIn`, `CheckOut` | Prioridade por ordem de chegada |
| Caixa | Receber pagamento | Ordem finalizada | Coins/Gorjeta | Entrega concluida | `PaymentStarted`, `PaymentDone` | Sem entrega nao ha pagamento |
| Loja de Produtos | Venda extra | Cliente, item | Receita adicional | Catalogo, estoque | `ItemSold` | Conversao varia por satisfacao |
| Hotel para Pets | Hospedagem | Animal, vaga | Receita por tempo | Alimentacao, limpeza | `HotelCheckIn`, `HotelPayout` | Receita em ticks de tempo |
| Veterinario | Tratamento premium | Animal, vet | Animal tratado + bonus | Nivel avancado | `VetStarted`, `VetEnded` | Desbloqueio tardio |

## Responsabilidades
- Processar servicos do loop principal.
- Ser ponto de consumo de recursos e geracao de valor.

## Dependencias
- [Animais](Animais.md)
- [Funcionarios](Funcionarios.md)
- [IA](IA.md)
- [Arquitetura](Arquitetura.md)

## Regras de Negocio
- Estacao ocupada nao aceita novo job.
- Falta de insumo pausa job e dispara alerta.
- Upgrade de estacao reduz tempo e aumenta qualidade.

## Eventos
- `StationUnlocked`
- `StationBusyChanged`
- `StationSupplyLow`
- `StationLevelUp`

## Fluxo Operacional
1. Receber job da fila.
2. Validar pre-condicoes.
3. Executar timer/animacao.
4. Emitir evento de conclusao.
5. Enviar output para proxima etapa.
