# Expansao do Mapa

Este documento define a progressao espacial do pet shop, incluindo fases de expansao, requisitos, custos, beneficios operacionais e impactos no core loop.

## Plano de Fases
| Fase | Nome | Custo (Coins) | Requisitos | Beneficios |
|---:|---|---:|---|---|
| 1 | Pequeno Pet Shop | 0 | Inicio do jogo | Loop basico ativo |
| 2 | Area de Banho Premium | 5,000 | Nivel Loja 5 | +1 estacao banho, +12% ticket banho |
| 3 | Area de Tosa | 18,000 | Nivel Loja 10 | Tosa desbloqueada, +20% ARPU por cliente |
| 4 | Hotel para Pets | 55,000 | Nivel Loja 16, 3 funcionarios | Receita passiva por hospedagem |
| 5 | Clinica Veterinaria | 140,000 | Nivel Loja 24, Vet contratado | Servicos premium e eventos de saude |
| 6 | Mega Pet Center | 350,000 | Nivel Loja 35, metas semanais | Multiplicador global + nova camada de meta |

## Responsabilidades
- Expandir variedade de loop e receita.
- Definir marcos de longo prazo.

## Dependencias
- [Economia](Economia.md)
- [Estacoes](Estacoes.md)
- [Progressao](Progressao.md)

## Regras de Negocio
- Toda expansao deve destravar ao menos 1 nova decisao de gameplay.
- Expansao nao pode causar queda de performance acima de 10% em devices alvo.

## Eventos
- `ExpansionAvailable`
- `ExpansionPurchased`
- `AreaUnlocked`

## Fluxo Operacional
1. Validar requisitos.
2. Exibir preview de custo/beneficio.
3. Confirmar compra.
4. Carregar conteudo (Addressables).
5. Atualizar rotas de NPC e spawn.
