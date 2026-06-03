# Animais

Este documento define os tipos de animais atendidos no jogo, seus parametros de servico, desbloqueios e modificadores que afetam o fluxo de trabalho e a economia.

## Tabela de Tipos de Animais
| Animal | Valor Base de Servico (Coins) | Tempo Base de Servico (s) | Nivel de Desbloqueio |
|---|---:|---:|---:|
| Cachorro pequeno | 35 | 18 | 1 |
| Cachorro medio | 55 | 26 | 3 |
| Cachorro grande | 85 | 36 | 8 |
| Gato | 50 | 24 | 2 |
| Coelho | 40 | 20 | 4 |
| Hamster | 22 | 12 | 1 |
| Papagaio | 70 | 30 | 10 |

## Modificadores
- Humor do animal: -10% a +15% no tempo.
- Limpeza da loja: +5% ticket com higiene alta.
- VIP cliente: +20% recompensa.

## Responsabilidades
- Definir custo-beneficio por especie/tamanho.
- Alimentar sistema de fila e estacoes.

## Dependencias
- [Game Loop](Game_Loop.md)
- [Estacoes](Estacoes.md)
- [Economia](Economia.md)

## Regras de Negocio
- Cada animal possui um pacote de necessidades minimas.
- Animais especiais nao aparecem antes do nivel minimo.

## Eventos
- `PetSpawned`
- `PetQueued`
- `PetMoodChanged`
- `PetServiceCompleted`

## Fluxo Operacional
1. Animal e registrado no check-in.
2. Sistema define servico e prioridade.
3. Executor atende na estacao correta.
4. Animal retorna para retirada.
