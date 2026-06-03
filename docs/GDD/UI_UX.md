# UI / UX

Este documento descreve a estrutura de interface e experiencia do usuario, com foco em clareza operacional, navegacao mobile e comunicacao eficiente de progresso, custo e recompensa.

## Diretrizes
- UI clara, legivel em telas pequenas.
- Feedback imediato para ganhos e bloqueios.
- Navegacao de no maximo 2 toques para features principais.

## Telas Principais
| Tela | Objetivo | Fluxo | Componentes | Navegacao |
|---|---|---|---|---|
| Tela Principal | Operar loja em tempo real | Jogar -> completar tarefas -> investir | HUD moedas, fila, mini objetivos | Botoes inferiores para modulos |
| Loja | Comprar itens e packs | Abrir loja -> selecionar categoria -> confirmar | Tabs, cards de item, CTA compra | Voltar para principal |
| Upgrades | Melhorar atributos | Abrir upgrades -> comparar ROI -> comprar | Lista upgrades, nivel atual/proximo | Atalho para estacao relacionada |
| Missoes | Gerenciar objetivos | Ver objetivos -> claim | Lista diaria/semanal, barra de progresso | Link para gameplay alvo |
| Eventos | Conteudo limitado | Entrar evento -> cumprir metas -> resgatar | Timer, milestones, premios | Retorno rapido para gameplay |
| Inventario | Ver recursos cosmeticos/itens | Filtrar -> equipar/usar | Slots, filtros, detalhes | Acesso por menu lateral |
| Configuracoes | Ajustes do jogo | Abrir -> alterar opcoes -> salvar | Audio, idioma, qualidade, conta | Fechar sem sair da sessao |

## Responsabilidades
- Expor estado de negocio ao jogador de forma intuitiva.
- Guiar decisao de investimento e prioridade.

## Dependencias
- [Gameplay](Gameplay.md)
- [Economia](Economia.md)
- [Monetizacao](Monetizacao.md)

## Regras de Negocio
- Elementos de compra devem exibir preco real e moeda.
- Alertas de erro devem indicar acao corretiva.

## Eventos
- `ScreenOpened`
- `ButtonClicked`
- `TooltipShown`
- `NavigationCompleted`

## Fluxo Operacional
1. HUD detecta contexto atual.
2. Exibe CTA prioritario.
3. Jogador navega para modulo.
4. Acao confirma e retorna ao loop.
