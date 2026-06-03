# Economia

Este documento define o modelo economico de PET SHOP ADMIN, incluindo moedas, fontes de receita, custos, regras de balanceamento e relacoes entre progressao, idle income e monetizacao.

## Moedas
- Coins: moeda principal para operacao e upgrades.
- Gems: moeda premium para aceleracao e conveniencia.

## Fontes de Receita
- Pagamento de servicos por animal.
- Venda de produtos na loja.
- Receita do hotel pet por tempo.
- Bonus de missao e eventos.
- Rewarded ads (boost temporario).

## Custos
- Contratacao e salario operacional de funcionarios.
- Upgrade de estacoes e atributos.
- Expansao de mapa.
- Reposicao de estoque de itens.

## Modelo de Balanceamento
- Receita base por ciclo: `R = clientes * ticketMedio * multiplicadores`.
- Custo de upgrade: `C(n) = C0 * (1.18^n)`.
- Tempo de retorno alvo por upgrade: 3 a 8 minutos (early), 20 a 60 minutos (mid), 2 a 8 horas (late).

## Escalabilidade
- Escala por camada: estacao -> area -> filial.
- Multiplicadores por eficiencia de funcionario e upgrades globais.

## Responsabilidades
- Definir ritmo de progressao economica.
- Manter fairness F2P com opcao premium de conveniencia.

## Dependencias
- [Upgrades](Upgrades.md)
- [Expansao](Expansao.md)
- [Monetizacao](Monetizacao.md)
- [Idle System](Idle_System.md)

## Regras de Negocio
- Premium nunca bloqueia conteudo essencial.
- Oferta de gem sempre opcional e transparente.
- Inflacao controlada por faixas de progressao.

## Eventos
- `RevenueGenerated`
- `ExpensePaid`
- `CurrencyChanged`
- `BoostActivated`

## Fluxo Operacional
1. Calcular receita por servicos concluidos.
2. Aplicar custos recorrentes e pontuais.
3. Atualizar saldos de Coins/Gems.
4. Liberar compras elegiveis.
5. Persistir snapshot economico.
