# Milestones - PET SHOP ADMIN

---

## Milestone 1: MVP (Semanas 1-4)

### Objetivo
Entregar o core loop jogável com todas as estações essenciais, economia funcional, save persistente e primeira camada de automação para validar retenção em soft launch.

### Funcionalidades Incluídas
- Loop principal completo (check-in → serviço → entrega → pagamento)
- Estações: Recepção, Banho, Tosa, Secagem, Caixa
- Animais base: cachorro pequeno/médio, gato, hamster
- 4 cargos de funcionário: recepcionista, banhista, tosador, faxineiro
- Upgrades essenciais (velocidade, capacidade, valor de serviço)
- Save local JSON versionado
- Economia de Coins funcional
- Expansão de área (1 desbloqueável)
- Player controller com joystick virtual
- HUD básico com moedas e fila

### Critérios de Conclusão
- [ ] Loop completo roda do check-in ao pagamento sem intervenção
- [ ] Sessão de 5 minutos mantém clareza de objetivo
- [ ] Build retém progresso entre sessões (save/load)
- [ ] Jogador alterna entre operação manual e suporte de NPC
- [ ] Build Android de smoke test executa em dispositivo médio
- [ ] Gargalos operacionais visíveis e solucionáveis por upgrade

---

## Milestone 2: Alpha (Semanas 4-5)

### Objetivo
Adicionar sistemas de retenção, monetização básica, idle income e polir a experiência dos primeiros 15 minutos para validação interna.

### Funcionalidades Incluídas
- Missões diárias (3 por dia)
- Conquistas básicas
- Login diário com recompensas
- Rewarded ads (boost de receita)
- Interstitial ads controlado
- Receita offline (idle income) com cap de 4h
- Starter Pack e Remove Ads (IAP mock)
- Audio placeholder e VFX leves
- Object pooling de entidades
- Onboarding / FTUE

### Critérios de Conclusão
- [ ] Rewarded ads entregam boost sem bloquear loop
- [ ] Missões diárias geram retorno ao jogo
- [ ] Receita offline calculada corretamente no retorno
- [ ] Fluxos críticos possuem navegação funcional em mobile
- [ ] Monetização não interrompe o loop principal em momentos críticos
- [ ] Object pooling elimina GC spikes em runtime

---

## Milestone 3: Beta (Semana 5-6)

### Objetivo
Otimizar performance, polir UX, corrigir bugs críticos e preparar analytics para soft launch com instrumentação completa.

### Funcionalidades Incluídas
- Otimização de pooling, draw calls e memória
- Instrumentação de analytics (eventos de funil)
- Balanceamento revisado de custos e recompensas
- Revisão de FTUE, tutoriais e textos
- Crash reporting integrado
- Validação de funil completo (tutorial → primeira compra → expansão → automação)
- Checklist de submissão Android

### Critérios de Conclusão
- [ ] FPS >= 30 estável em dispositivos mid-tier
- [ ] Memória dentro do budget para Android mid
- [ ] Eventos de analytics rastreiam funil completo
- [ ] Zero bugs críticos de loop, save ou economia
- [ ] Crash rate < 1% em testes internos

---

## Milestone 4: Release 1.0 - Soft Launch (Pós Semana 6)

### Objetivo
Lançar em região limitada para coleta de métricas reais de retenção e monetização, iterando com base em dados.

### Funcionalidades Incluídas
- Release candidate estável
- Dashboards de KPIs configurados
- Store assets e material de lançamento
- Build de soft launch publicada
- Monitoramento diário ativo

### Critérios de Conclusão
- [ ] D1 >= 40%
- [ ] D7 >= 15%
- [ ] ARPDAU medido e reportado
- [ ] Fill rate rewarded ads >= 80%
- [ ] Crash rate < 0.5% em produção
- [ ] Jogo executa com estabilidade em sessões repetidas
- [ ] KPIs iniciais têm instrumentação mínima para leitura pós-lançamento
