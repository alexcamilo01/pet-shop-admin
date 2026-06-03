# Backlog Inicial

## Visao
Backlog inicial estruturado por épicos para suportar o MVP e o primeiro ciclo de soft launch de PET SHOP ADMIN.

## Prioridades
- P0: Essencial para MVP.
- P1: Importante para retenção e monetização inicial.
- P2: Pós-MVP ou melhoria incremental.

## Epico 1 - Core Loop Operacional

### Feature: Check-in de clientes e pets
- User Story: Como jogador, quero receber clientes e registrar seus pets para iniciar o serviço.
- Critérios de Aceitação:
  - Cliente chega à recepção com animação de entrada.
  - O pet é registrado com tipo de serviço.
  - Um slot de fila é criado corretamente.
- Prioridade: P0

### Feature: Transporte manual de pets
- User Story: Como jogador, quero pegar um pet e levá-lo até a estação correta.
- Critérios de Aceitação:
  - O jogador só pode transportar até sua capacidade atual.
  - A estação correta aceita apenas pets elegíveis.
  - O feedback visual indica quando o pet foi entregue.
- Prioridade: P0

### Feature: Execução do serviço de banho
- User Story: Como jogador, quero concluir o banho para liberar o pet ao cliente.
- Critérios de Aceitação:
  - O banho possui tempo configurável.
  - O estado do pet muda para pronto ao final.
  - O cliente pode seguir para retirada após conclusão.
- Prioridade: P0

### Feature: Pagamento no caixa
- User Story: Como jogador, quero receber pagamento pelos serviços concluídos.
- Critérios de Aceitação:
  - O pagamento só ocorre após entrega do pet.
  - O HUD atualiza `Coins` imediatamente.
  - Analytics registra valor recebido.
- Prioridade: P0

## Epico 2 - Progressao e Expansao

### Feature: Upgrades do jogador
- User Story: Como jogador, quero melhorar minha velocidade e capacidade para operar mais rápido.
- Critérios de Aceitação:
  - Cada upgrade possui custo e nível máximo configuráveis.
  - O efeito é aplicado em runtime sem reiniciar a cena.
  - O custo cresce por curva definida em balance config.
- Prioridade: P0

### Feature: Desbloqueio de estações
- User Story: Como jogador, quero abrir novas áreas para aumentar a capacidade do pet shop.
- Critérios de Aceitação:
  - Cada expansão possui requisito e custo.
  - A área desbloqueada altera navmesh, fluxo e capacidade.
  - O save persiste o estado da expansão.
- Prioridade: P0

### Feature: Desbloqueio de espécies
- User Story: Como jogador, quero atender novos tipos de animais conforme avanço.
- Critérios de Aceitação:
  - Novas espécies entram na tabela de spawn por nível.
  - Valores e tempos de serviço são carregados por dados.
  - A UI comunica o novo desbloqueio.
- Prioridade: P1

## Epico 3 - Funcionarios e Automacao

### Feature: Contratação de recepcionista
- User Story: Como jogador, quero contratar uma recepcionista para automatizar o check-in.
- Critérios de Aceitação:
  - A recepcionista coleta clientes na fila de entrada.
  - O tempo médio de check-in cai após contratação.
  - O comportamento usa a state machine padrão.
- Prioridade: P0

### Feature: Contratação de banhista
- User Story: Como jogador, quero automatizar o banho para liberar meu foco a outras tarefas.
- Critérios de Aceitação:
  - O banhista busca pets na fila correta.
  - O serviço respeita eficiência do funcionário.
  - O sistema evita dupla alocação da mesma tarefa.
- Prioridade: P0

### Feature: Faxineiro
- User Story: Como jogador, quero manter a loja limpa para preservar eficiência e satisfação.
- Critérios de Aceitação:
  - Sujeira surge por eventos de uso.
  - O faxineiro prioriza manchas críticas.
  - Ambientes limpos mantêm throughput máximo.
- Prioridade: P1

## Epico 4 - Retencao

### Feature: Missões diárias
- User Story: Como jogador, quero receber objetivos diários para ter metas claras de retorno.
- Critérios de Aceitação:
  - Três missões são geradas por dia.
  - Recompensas incluem `Coins`, `Gems` ou boosters leves.
  - As missões resetam em horário configurável.
- Prioridade: P1

### Feature: Conquistas
- User Story: Como jogador, quero desbloquear marcos permanentes que recompensem meu progresso.
- Critérios de Aceitação:
  - Cada conquista possui condição rastreável.
  - O prêmio só pode ser coletado uma vez.
  - O histórico persiste entre sessões.
- Prioridade: P1

### Feature: Login diário
- User Story: Como jogador, quero receber recompensas por dias consecutivos de acesso.
- Critérios de Aceitação:
  - A sequência diária é salva localmente.
  - Há recompensa destaque no dia 7.
  - O fluxo é apresentado no primeiro login do dia.
- Prioridade: P1

## Epico 5 - Monetizacao

### Feature: Rewarded ad de bônus operacional
- User Story: Como jogador, quero assistir um anúncio opcional para acelerar minha progressão sem pagar.
- Critérios de Aceitação:
  - O bônus tem valor claro e duração limitada.
  - A oferta nunca bloqueia a ação principal.
  - O cooldown da oferta é configurável.
- Prioridade: P1

### Feature: Remove Ads
- User Story: Como jogador pagante, quero remover interstitials para jogar sem interrupções.
- Critérios de Aceitação:
  - A compra remove apenas anúncios intersticiais.
  - Rewarded ads continuam opcionais.
  - O estado é restaurado após reinstalação quando houver suporte futuro.
- Prioridade: P1

### Feature: Starter Pack
- User Story: Como novo jogador, quero uma oferta inicial de alto valor percebido.
- Critérios de Aceitação:
  - A oferta aparece após marco de progressão definido.
  - Contém `Gems`, `Coins` e item/booster de conveniência.
  - O pacote expira após janela limitada.
- Prioridade: P1

## Epico 6 - Infraestrutura Tecnica

### Feature: Save versionado
- User Story: Como sistema, quero versionar saves para migrar dados sem perda de progresso.
- Critérios de Aceitação:
  - O save contém campo de versão.
  - Há fallback para arquivo íntegro anterior.
  - Falhas de leitura não causam crash.
- Prioridade: P0

### Feature: Object pooling de entidades
- User Story: Como sistema, quero reutilizar clientes, pets e VFX para reduzir custo de CPU e GC.
- Critérios de Aceitação:
  - Pools são configuráveis por capacidade inicial e máxima.
  - Spawn/despawn não gera alocação excessiva em runtime.
  - O comportamento permanece transparente para controllers.
- Prioridade: P0

### Feature: Instrumentação de analytics
- User Story: Como product owner, quero medir eventos críticos para calibrar retenção e monetização.
- Critérios de Aceitação:
  - Eventos de check-in, serviço, pagamento, upgrade e ad impression são enviados.
  - Parâmetros mínimos incluem valor, estação e estágio de progressão.
  - O sistema permite desligar telemetria em ambiente local.
- Prioridade: P1

## Dependencias Gerais
- Core loop concluído antes de monetização.
- Save básico concluído antes de login diário e metas persistentes.
- Tabelas de dados concluídas antes do balanceamento final.# Backlog Inicial - PET SHOP ADMIN

## Estrutura
Cada item esta organizado por epico, feature e user stories com criterios de aceitacao e prioridade.

## Epico 1 - Core Loop Operacional

### Feature 1.1 - Check-in de Clientes
**User Story:** Como jogador, quero receber clientes e registrar seus pets para iniciar servicos e gerar receita.

**Criterios de Aceitacao**
- Cliente spawna conforme taxa configurada.
- Recepcao identifica tipo de pet e servico solicitado.
- Pet entra corretamente na fila associada.
- UI mostra fila e status do atendimento.

**Prioridade:** P0

### Feature 1.2 - Estacao de Banho
**User Story:** Como jogador, quero levar o animal para banho e concluir o servico para receber pagamento.

**Criterios de Aceitacao**
- Animal pode ser transportado ate a estacao valida.
- Servico inicia apenas quando requisitos forem atendidos.
- Tempo de execucao respeita configuracao do animal e upgrades.
- Ao concluir, o animal muda para estado pronto para entrega.

**Prioridade:** P0

### Feature 1.3 - Entrega e Pagamento
**User Story:** Como jogador, quero devolver o animal ao cliente e receber coins para reinvestir na loja.

**Criterios de Aceitacao**
- Cliente aguarda o termino do servico.
- Entrega correta dispara pagamento no caixa.
- Valor recebido respeita tabela de servico e modificadores ativos.
- Evento analitico de receita e registrado.

**Prioridade:** P0

## Epico 2 - Progressao e Expansao

### Feature 2.1 - Sistema de Upgrades
**User Story:** Como jogador, quero comprar melhorias para aumentar eficiencia e throughput da loja.

**Criterios de Aceitacao**
- Cada upgrade possui custo, nivel maximo e efeito configuravel.
- A compra desconta coins ou gems corretamente.
- O efeito e aplicado imediatamente no sistema alvo.
- UI indica beneficio incremental antes da compra.

**Prioridade:** P0

### Feature 2.2 - Expansao de Areas
**User Story:** Como jogador, quero desbloquear novas areas para oferecer mais servicos e crescer a loja.

**Criterios de Aceitacao**
- Cada area possui custo e requisito de progressao.
- Ao comprar, a area e liberada visual e funcionalmente.
- Novas estacoes entram no loop sem reiniciar a cena.
- Save persiste o estado da expansao.

**Prioridade:** P1

## Epico 3 - Automacao por Funcionarios

### Feature 3.1 - Contratacao de Funcionarios
**User Story:** Como jogador, quero contratar funcionarios para automatizar tarefas repetitivas.

**Criterios de Aceitacao**
- Funcionarios possuem custo inicial e upkeep abstrato no balance.
- Cada role executa apenas tarefas compativeis.
- Estado visual e logico do funcionario e atualizado corretamente.
- Contratacao e persistida no save.

**Prioridade:** P1

### Feature 3.2 - IA de State Machine
**User Story:** Como equipe de desenvolvimento, queremos uma IA previsivel para escalar a automacao com baixo risco tecnico.

**Criterios de Aceitacao**
- Estados `Idle`, `MoveToTask`, `ExecuteTask`, `Return` e `Break` implementados.
- Transicoes disparam por eventos e validacoes deterministicas.
- IA recupera de tarefa cancelada sem travar o loop.
- Logs de depuracao podem ser habilitados por ambiente.

**Prioridade:** P1

## Epico 4 - Economia, Idle e Save

### Feature 4.1 - Economia de Coins e Gems
**User Story:** Como jogador, quero entender claramente meus ganhos e gastos para planejar minha progressao.

**Criterios de Aceitacao**
- Coins e gems aparecem com feedback claro em UI.
- Toda transacao gera entrada de analytics.
- Custos por faixa de progressao podem ser ajustados sem alterar codigo.
- Nao ha fontes invisiveis de desconto ou custo.

**Prioridade:** P0

### Feature 4.2 - Receita Offline
**User Story:** Como jogador, quero receber receita enquanto estou fora do jogo para sentir progresso continuo.

**Criterios de Aceitacao**
- Receita offline usa janela maxima configuravel.
- Calculo considera funcionarios e estacoes desbloqueadas.
- UI de retorno mostra total ganho e opcao de boost.
- Exploits obvios de horario sao mitigados por validacao simples.

**Prioridade:** P1

### Feature 4.3 - Save/Load Local
**User Story:** Como jogador, quero recuperar meu progresso ao reabrir o jogo sem perder compras ou expansoes.

**Criterios de Aceitacao**
- Save ocorre em gatilhos criticos e autosave.
- Load restaura moedas, upgrades, funcionarios, construcoes e missoes.
- Sistema trata versao e arquivo invalido com fallback seguro.
- Corrupcao parcial nao quebra o boot do jogo.

**Prioridade:** P0

## Epico 5 - Retencao e Meta Systems

### Feature 5.1 - Missoes Diarias e Semanais
**User Story:** Como jogador, quero objetivos recorrentes para voltar ao jogo e receber recompensas adicionais.

**Criterios de Aceitacao**
- Missoes geram objetivos claros e rastreaveis.
- Claim entrega recompensa correta e unica.
- Reset diario e semanal respeita horario configurado.
- Sistema suporta tags por categoria de objetivo.

**Prioridade:** P1

### Feature 5.2 - Conquistas
**User Story:** Como jogador, quero desbloquear conquistas por marcos de desempenho para aumentar engajamento de medio prazo.

**Criterios de Aceitacao**
- Conquistas possuem condicao, status e recompensa.
- Claims nao podem ser repetidos indevidamente.
- UI mostra progresso parcial quando aplicavel.
- Eventos de gameplay alimentam o tracker automaticamente.

**Prioridade:** P2

## Epico 6 - Monetizacao e Live Ops Base

### Feature 6.1 - Rewarded Ads
**User Story:** Como jogador, quero assistir anuncios opcionais para obter recompensas de conveniencia.

**Criterios de Aceitacao**
- Oferta e opcional e contextualizada.
- Recompensa e entregue apenas apos callback de conclusao valida.
- Cooldowns e limites sao aplicados por tipo de reward.
- Eventos de impressao, start e completion sao enviados para analytics.

**Prioridade:** P1

### Feature 6.2 - IAP Basica
**User Story:** Como jogador, quero comprar pacotes de valor claro sem sentir obrigacao para progredir.

**Criterios de Aceitacao**
- Produtos `Remove Ads`, `Starter Pack`, `Gem Pack` e `VIP Pack` cadastrados.
- Restauracao de compra esta disponivel quando suportado pela plataforma.
- Beneficios comprados sao refletidos imediatamente no perfil.
- Mensagens de oferta respeitam guardrails de UX e F2P justo.

**Prioridade:** P2

## Ordenacao Inicial de Entrega
1. P0: Core loop, economia, save.
2. P1: automacao, expansao, idle, missoes, rewarded ads.
3. P2: conquistas, IAP completa, live ops expandido.

## Dependencias
- [Roadmap](../Roadmap/Roadmap.md)
- [MVP](../GDD/MVP.md)
- [Game Loop](../GDD/Game_Loop.md)