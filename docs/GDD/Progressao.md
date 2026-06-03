# Progressao

Este documento organiza a progressao do jogador ao longo do produto, detalhando marcos de desbloqueio, ritmo de crescimento e relacao entre conteudo novo, investimento e retencao.

## Macro Progressao
- Nivel da Loja: desbloqueia estacoes e expansoes.
- Nivel do Jogador: melhora mobilidade e capacidade.
- Nivel de Equipe: aumenta automacao.

## Curva de Progressao
- Early (Niveis 1-10): foco em onboarding e primeira automacao.
- Mid (Niveis 11-30): multiplicadores, hotel pet e especializacao.
- Late (Niveis 31+): clinica, meta de mega center, eventos sazonais.

## Gate de Conteudo
- Requisitos por Coins, nivel e milestones de missao.
- Soft gate por tempo de servico e fila.

## Responsabilidades
- Definir ritmo de desbloqueio.
- Evitar estagnacao de gameplay.

## Dependencias
- [Economia](Economia.md)
- [Expansao](Expansao.md)
- [Missoes](Missoes.md)

## Regras de Negocio
- Sempre existir ao menos 2 objetivos ativos visiveis.
- Cada novo modulo deve aumentar receita potencial em >= 15%.

## Eventos
- `LevelUp`
- `MilestoneUnlocked`
- `ProgressionStalled`

## Fluxo Operacional
1. Jogador acumula XP por tarefas e receita.
2. Sistema valida requisitos de desbloqueio.
3. Conteudo novo e habilitado.
4. UI guia proxima meta recomendada.
