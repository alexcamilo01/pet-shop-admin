# Roadmap de Desenvolvimento

## Objetivo
Planejar seis semanas de produção até o lançamento do MVP, com foco em execução enxuta, ativos gratuitos e validação contínua do core loop.

## Premissas
- Time base: 1 game designer, 2 gameplay programmers, 1 technical artist/UI, 1 generalist 3D, 1 QA parcial.
- Plataforma alvo inicial: Android, com iOS em preparação de pipeline.
- Todos os assets do MVP devem ser gratuitos ou produzidos internamente.

## Semana 1 - Foundation Sprint
### Objetivos
- Formalizar visão, escopo e backlog.
- Configurar projeto Unity 6 com URP, Input System e Addressables.
- Prototipar movimentação do jogador, câmera e interação base.

### Entregas
- Projeto Unity configurado.
- Cena sandbox do pet shop inicial.
- Player controller com joystick virtual.
- Estrutura base de managers, services e save bootstrap.

### Critérios de Saida
- Jogador se move, interage e transporta um pet placeholder.
- Build Android de smoke test executa em dispositivo médio.

## Semana 2 - Core Loop Vertical Slice
### Objetivos
- Implementar recepção, fila, banho, entrega e pagamento.
- Integrar economia básica em `Coins`.
- Validar leitura do loop por playtest interno.

### Entregas
- Cliente chega, entrega pet e aguarda.
- Estação de banho funcional.
- Caixa processa pagamento e atualiza HUD.
- Primeiros efeitos sonoros e feedbacks visuais.

### Critérios de Saida
- Loop completo roda do check-in ao pagamento sem intervenção externa.
- Sessão inicial de 5 minutos mantém clareza de objetivo.

## Semana 3 - Staff, IA e Progressao
### Objetivos
- Implementar contratação de funcionários e state machine base.
- Adicionar upgrades iniciais do jogador e da estação.
- Introduzir progressão por desbloqueio de animais e throughput.

### Entregas
- Recepcionista, banhista e faxineiro funcionais.
- Sistema de upgrades globais e por estação.
- Tabelas de balanceamento iniciais em Scriptable Objects.

### Critérios de Saida
- Jogador consegue alternar entre operação manual e suporte de NPC.
- Gargalos operacionais ficam visíveis e solucionáveis por upgrade.

## Semana 4 - Conteudo do MVP
### Objetivos
- Adicionar tosa, secagem, loja de produtos e primeira expansão.
- Implementar missões diárias, conquistas básicas e save persistente.
- Consolidar HUD e telas principais.

### Entregas
- Área de tosa desbloqueável.
- Save/load local com cálculo offline.
- Telas de upgrades, loja, missões e configurações.
- Conjunto inicial de metas de retenção.

### Critérios de Saida
- Build retém progresso entre sessões.
- Fluxos críticos possuem navegação funcional em mobile.

## Semana 5 - Monetizacao, Polimento e Performance
### Objetivos
- Integrar rewarded ads, remove ads e starter pack.
- Otimizar pooling, draw calls e uso de memória.
- Melhorar onboarding, feedbacks e pacing dos primeiros 15 minutos.

### Entregas
- Pontos opcionais de rewarded ads.
- Interstitial controlado por contexto.
- Checklist de otimização aplicado na cena principal.
- Balanceamento revisado de custos e recompensas.

### Critérios de Saida
- FPS e memória adequados para aparelhos mid-tier.
- Monetização não interrompe o loop principal em momentos críticos.

## Semana 6 - Soft Launch Readiness
### Objetivos
- Corrigir bugs críticos.
- Refinar analytics, funil de conversão e tuning de retenção.
- Preparar arte final mínima, store assets e build candidata.

### Entregas
- Release candidate do MVP.
- Lista de bugs priorizada e estabilizada.
- Dashboards de eventos principais definidos.
- Material de soft launch pronto.

### Critérios de Saida
- Jogo executa com estabilidade em sessões repetidas.
- KPIs iniciais têm instrumentação mínima para leitura pós-lançamento.

## Marco de Lancamento
- Soft launch regional ao final da semana 6.
- Janela de 2 a 4 semanas para coleta de métricas e ajustes antes de escala.

## Dependencias Criticas
- Definição final de tuning de economia até semana 4.
- Disponibilidade de assets gratuitos compatíveis com estilo low poly cartoon.
- Integração de ads/IAP em ambiente de testes até semana 5.

## Pos-MVP
- Hotel para Pets completo.
- Veterinário e casos especiais.
- Eventos sazonais.
- Cloud save.
- Mais espécies, cosméticos e rede multiunidade.# Roadmap de Producao - PET SHOP ADMIN

## Objetivo
Guiar a execucao do projeto do pre-producao ao lancamento inicial com foco em MVP validavel, soft launch e preparacao operacional.

## Premissas
- Time base: 1 game designer/produto, 2 programadores Unity, 1 artista generalista, 1 QA compartilhado.
- Escopo inicial com assets gratuitos e visual low poly/cartoon.
- Plataforma alvo: Android primeiro, iOS em seguida com paridade de conteudo.

## Semana 1 - Pre-producao e Foundations
- Consolidar documentacao oficial e backlog inicial.
- Definir KPIs de produto: D1, D7, ARPDAU, Fill Rate Ads, RPM.
- Configurar projeto Unity 6 com URP, New Input System e Addressables.
- Implementar arquitetura base: managers, services, controllers e data layer.
- Criar prototipo jogavel com movimentacao do player e mapa inicial do pet shop.
- Definir pacote inicial de assets gratuitos e pipeline de importacao.

## Semana 2 - Core Loop Jogavel
- Implementar recepcao, fila de pets e uma estacao de banho funcional.
- Implementar ciclo completo: cliente chega, entrega animal, servico, pagamento.
- Criar economia inicial de coins com UI basica de saldo.
- Implementar dados de animais e tabelas de servico via Scriptable Objects.
- Instrumentar eventos analiticos basicos do loop principal.

## Semana 3 - Automacao e Progressao Inicial
- Implementar funcionarios base: recepcionista, banhista e faxineiro.
- Implementar state machine de IA com atribuicao de tarefas.
- Implementar upgrades de velocidade, capacidade e valor de servico.
- Adicionar limpeza e reposicao simples como tarefas auxiliares.
- Criar primeira expansao da loja e onboarding de progressao.

## Semana 4 - Conteudo MVP e Retencao Basica
- Implementar tosa, secagem e loja de produtos.
- Integrar missoes diarias simples, conquistas iniciais e login diario.
- Implementar save/load em JSON com autosave e restauracao robusta.
- Adicionar audio placeholder, VFX leves e UX de feedback.
- Rodar primeira bateria de balanceamento do early game.

## Semana 5 - Monetizacao, Idle e Otimizacao
- Integrar rewarded ads e camada inicial de IAP mock/real conforme ambiente.
- Implementar idle income offline com limite de horas acumuladas.
- Aplicar object pooling, addressables e revisao de draw calls.
- Ajustar pacing de upgrades, contratacoes e expansoes.
- Testar performance em dispositivos Android mid e low tier.

## Semana 6 - Polimento, QA e Lancamento Inicial
- Fechar bugs criticos de loop, save e economia.
- Revisar FTUE, tutoriais, textos de UI e mensagens de monetizacao.
- Validar funil completo: tutorial, primeira compra, primeira expansao, primeira automacao.
- Preparar build de soft launch com analytics, crash reporting e loja.
- Executar checklist de submissao Android e preparar backlog pos-lancamento.

## Marco de Lancamento
- Soft launch regional com monitoramento diario.
- Ajustes de economia, ads e retencao na primeira semana operacional.
- Gate para expansao de plataforma apos estabilidade de KPI e crash rate.

## Entregaveis por Fase
- Semana 1: projeto configurado e vertical slice tecnico.
- Semana 2: core loop funcional end-to-end.
- Semana 3: automacao e primeira camada de progressao.
- Semana 4: MVP completo em conteudo base.
- Semana 5: monetizacao + idle + performance.
- Semana 6: soft launch ready.

## Dependencias
- [MVP](../GDD/MVP.md)
- [Arquitetura](../GDD/Arquitetura.md)
- [Monetizacao](../GDD/Monetizacao.md)
- [Otimizacao](../GDD/Otimizacao.md)