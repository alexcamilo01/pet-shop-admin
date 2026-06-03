# Visao Geral

Este documento consolida o posicionamento do produto, seus pilares de design, objetivos de negocio e criterios macro para orientar decisao de escopo e direcao do projeto.

## Pitch
Construa, automatize e expanda um pet shop de bairro para um Mega Pet Center com servicos premium, hotel e clinica veterinaria.

## Objetivos de Produto
- Entregar ciclo idle de alta clareza e baixa friccao.
- Permitir progressao diaria com metas de curto, medio e longo prazo.
- Suportar monetizacao etica sem pay to win.

## Publico-Alvo
- Jogadores de idle tycoon e simulation em mobile.
- Sessoes de 3 a 12 minutos com retorno frequente.

## KPIs de Negocio
- D1 >= 40%
- D7 >= 15%
- D30 >= 6%
- ARPDAU alvo: US$ 0.12
- Fill rate rewarded ads >= 80%

## Pilares de Design
1. Clareza operacional: jogador sempre sabe qual tarefa da mais retorno.
2. Automacao progressiva: funcionarios assumem rotinas repetitivas.
3. Satisfacao visual: feedback de servico concluido e crescimento da loja.
4. Escala de negocio: expansoes desbloqueiam novos loops.

## Responsabilidades
- Definir visao macro do produto.
- Garantir alinhamento entre design, engenharia e monetizacao.

## Dependencias
- [Gameplay](Gameplay.md)
- [Economia](Economia.md)
- [Progressao](Progressao.md)
- [MVP](MVP.md)

## Regras de Negocio
- Todo sistema deve reforcar o loop principal de atendimento e crescimento.
- Features novas entram por validacao de KPI e custo de producao.

## Eventos
- `GameStarted`
- `SessionEnded`
- `KPITracked`

## Fluxo Operacional
1. Definir meta de release.
2. Priorizar backlog.
3. Implementar e instrumentar analytics.
4. Rodar balance pass.
5. Publicar build e medir impacto.
