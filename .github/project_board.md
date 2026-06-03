# GitHub Project Board - PET SHOP ADMIN

## Estrutura de Colunas

| Coluna | Descrição | Critérios de Entrada | Critérios de Saída |
|--------|-----------|---------------------|-------------------|
| **Backlog** | Itens identificados mas não priorizados para sprint atual | Issue criada com descrição e labels | Priorizada e estimada |
| **Ready** | Itens priorizados, estimados e sem bloqueios | Dependências resolvidas, critérios claros | Desenvolvedor atribuído |
| **In Progress** | Em desenvolvimento ativo | Branch criada, dev atribuído | PR aberto |
| **Review** | Aguardando code review ou design review | PR aberto com checklist completo | Aprovação obtida |
| **Testing** | Em QA / teste funcional | PR aprovado, build disponível | Testes passam, sem regressão |
| **Done** | Concluído e merged | Merged na branch principal | N/A |
| **Blocked** | Impedido por dependência externa ou técnica | Bloqueio identificado e documentado | Bloqueio resolvido → volta para coluna anterior |

---

## Épicos

### Epic 1: Core Loop Operacional
- **Descrição:** Loop principal de atendimento do pet shop — do check-in do cliente até o pagamento.
- **Objetivo:** Validar que o ciclo de valor é claro, funcional e repetível.
- **Dependências:** Arquitetura base, Player Controller
- **Critérios de Conclusão:**
  - Loop completo (check-in → serviço → entrega → pagamento) funcional
  - Pelo menos 3 tipos de animais atendidos
  - Tempo de sessão médio de 5 min com clareza de objetivo
- **Labels:** `type:epic`, `system:gameplay`, `priority:p0-critical`

### Epic 2: Progressão e Expansão
- **Descrição:** Sistemas de crescimento do jogador — upgrades, desbloqueio de áreas e espécies.
- **Objetivo:** Garantir que o jogador sempre tem um próximo objetivo claro e acessível.
- **Dependências:** Core Loop, Economia
- **Critérios de Conclusão:**
  - Upgrades de velocidade, capacidade e valor funcionais
  - Pelo menos 1 expansão de área desbloqueável
  - Progressão visível na UI
- **Labels:** `type:epic`, `system:gameplay`, `priority:p0-critical`

### Epic 3: Funcionários e Automação
- **Descrição:** Sistema de contratação e IA de funcionários para automatizar tarefas repetitivas.
- **Objetivo:** Permitir operação hands-off parcial e escalar throughput da loja.
- **Dependências:** Core Loop, Estações, IA State Machine
- **Critérios de Conclusão:**
  - Recepcionista, banhista e faxineiro funcionais
  - State machine com estados Idle/MoveToTask/ExecuteTask/Return/Break
  - Funcionários persistidos no save
- **Labels:** `type:epic`, `system:ai`, `priority:p0-critical`

### Epic 4: Economia, Idle e Save
- **Descrição:** Sistemas de moeda, receita offline e persistência de dados.
- **Objetivo:** Sustentar progressão contínua e proteger dados do jogador.
- **Dependências:** Core Loop
- **Critérios de Conclusão:**
  - Coins e Gems funcionais com feedback em UI
  - Receita offline calculada corretamente (cap 4h)
  - Save/Load local com versionamento e fallback
- **Labels:** `type:epic`, `system:economy`, `priority:p0-critical`

### Epic 5: Retenção e Meta Systems
- **Descrição:** Missões diárias, conquistas e login diário para engajamento recorrente.
- **Objetivo:** Criar razões claras para o jogador retornar diariamente.
- **Dependências:** Economia, Save System
- **Critérios de Conclusão:**
  - 3 missões diárias geradas e rastreáveis
  - Conquistas com progresso parcial visível
  - Login diário com sequência e recompensa dia 7
- **Labels:** `type:epic`, `system:retention`, `priority:p1-high`

### Epic 6: Monetização e Live Ops
- **Descrição:** Rewarded ads, interstitial, IAPs e ofertas contextuais.
- **Objetivo:** Sustentar receita sem comprometer experiência F2P.
- **Dependências:** Economia, Core Loop, UI
- **Critérios de Conclusão:**
  - Rewarded ads opt-in funcional
  - Interstitial com guardrail de 4 min
  - Remove Ads, Starter Pack e Gem Pack registrados
- **Labels:** `type:epic`, `system:monetization`, `priority:p1-high`

### Epic 7: Infraestrutura Técnica
- **Descrição:** Arquitetura base, object pooling, analytics e otimização de performance.
- **Objetivo:** Garantir base técnica sólida, escalável e mensurável.
- **Dependências:** Nenhuma (fundação)
- **Critérios de Conclusão:**
  - Projeto Unity 6 configurado com URP, Input System e Addressables
  - Object pooling de clientes, pets e VFX
  - Analytics instrumentado para eventos críticos
  - FPS estável em dispositivos mid-tier
- **Labels:** `type:epic`, `system:infrastructure`, `priority:p0-critical`

### Epic 8: UI/UX
- **Descrição:** Interface, HUD, telas e navegação do jogo.
- **Objetivo:** Expor estado do jogo ao jogador de forma clara e acessível em mobile.
- **Dependências:** Core Loop, Economia
- **Critérios de Conclusão:**
  - HUD com moedas, fila e mini-objetivos
  - Telas de upgrades, loja, missões e configurações
  - Navegação de no máximo 2 toques para features principais
- **Labels:** `type:epic`, `system:ui`, `priority:p1-high`

### Epic 9: Audio e Polish
- **Descrição:** Efeitos sonoros, música e feedback sensorial.
- **Objetivo:** Aumentar satisfação visual e auditiva do jogador.
- **Dependências:** Core Loop, Estações
- **Critérios de Conclusão:**
  - SFX para ações principais (serviço, pagamento, upgrade)
  - BGM loop para gameplay
  - VFX leves para feedback de conclusão
- **Labels:** `type:epic`, `system:audio`, `priority:p2-medium`

---

## Features por Épico

### Epic 1: Core Loop Operacional
| # | Feature | Prioridade | Milestone |
|---|---------|-----------|-----------|
| F1.1 | Check-in de Clientes e Pets | P0 | MVP |
| F1.2 | Transporte Manual de Pets | P0 | MVP |
| F1.3 | Estação de Banho | P0 | MVP |
| F1.4 | Estação de Tosa | P0 | MVP |
| F1.5 | Estação de Secagem | P0 | MVP |
| F1.6 | Entrega e Pagamento no Caixa | P0 | MVP |
| F1.7 | Sistema de Fila por Serviço | P0 | MVP |

### Epic 2: Progressão e Expansão
| # | Feature | Prioridade | Milestone |
|---|---------|-----------|-----------|
| F2.1 | Sistema de Upgrades (Jogador e Estações) | P0 | MVP |
| F2.2 | Expansão de Áreas | P1 | MVP |
| F2.3 | Desbloqueio de Espécies | P1 | Alpha |

### Epic 3: Funcionários e Automação
| # | Feature | Prioridade | Milestone |
|---|---------|-----------|-----------|
| F3.1 | Contratação de Funcionários | P1 | MVP |
| F3.2 | IA State Machine Base | P1 | MVP |
| F3.3 | Recepcionista Autônomo | P0 | MVP |
| F3.4 | Banhista Autônomo | P0 | MVP |
| F3.5 | Faxineiro Autônomo | P1 | Alpha |

### Epic 4: Economia, Idle e Save
| # | Feature | Prioridade | Milestone |
|---|---------|-----------|-----------|
| F4.1 | Economia de Coins e Gems | P0 | MVP |
| F4.2 | Save/Load Local Versionado | P0 | MVP |
| F4.3 | Receita Offline (Idle Income) | P1 | Alpha |

### Epic 5: Retenção e Meta Systems
| # | Feature | Prioridade | Milestone |
|---|---------|-----------|-----------|
| F5.1 | Missões Diárias e Semanais | P1 | Alpha |
| F5.2 | Conquistas | P2 | Beta |
| F5.3 | Login Diário | P1 | Alpha |

### Epic 6: Monetização e Live Ops
| # | Feature | Prioridade | Milestone |
|---|---------|-----------|-----------|
| F6.1 | Rewarded Ads | P1 | Alpha |
| F6.2 | Interstitial Ads | P1 | Alpha |
| F6.3 | IAP (Remove Ads, Starter Pack, Gem Pack) | P2 | Beta |

### Epic 7: Infraestrutura Técnica
| # | Feature | Prioridade | Milestone |
|---|---------|-----------|-----------|
| F7.1 | Setup Projeto Unity 6 (URP, Input, Addressables) | P0 | MVP |
| F7.2 | Arquitetura Base (Managers, Services, Controllers) | P0 | MVP |
| F7.3 | Object Pooling | P0 | MVP |
| F7.4 | Instrumentação de Analytics | P1 | Alpha |
| F7.5 | Otimização de Performance | P1 | Beta |

### Epic 8: UI/UX
| # | Feature | Prioridade | Milestone |
|---|---------|-----------|-----------|
| F8.1 | HUD Principal (Moedas, Fila, Objetivos) | P0 | MVP |
| F8.2 | Tela de Upgrades | P0 | MVP |
| F8.3 | Tela de Loja/Contratação | P1 | Alpha |
| F8.4 | Tela de Missões | P1 | Alpha |
| F8.5 | Tela de Configurações | P2 | Beta |
| F8.6 | Onboarding / FTUE | P1 | Alpha |

### Epic 9: Audio e Polish
| # | Feature | Prioridade | Milestone |
|---|---------|-----------|-----------|
| F9.1 | SFX de Ações Principais | P2 | Alpha |
| F9.2 | BGM Loop | P2 | Beta |
| F9.3 | VFX de Feedback | P2 | Alpha |

---

## Issues Detalhadas

### Issue: Setup Projeto Unity 6
- **Descrição:** Configurar projeto Unity 6 com URP, New Input System e Addressables. Criar estrutura de pastas conforme arquitetura definida.
- **Critérios de Aceite:**
  - Projeto compila sem erros
  - URP renderiza cena de teste
  - Input System configurado com joystick virtual
  - Addressables group criado
  - Estrutura de pastas conforme `docs/GDD/Arquitetura.md`
- **Dependências:** Nenhuma
- **Estimativa:** 4h
- **Prioridade:** P0
- **Milestone:** MVP
- **Labels:** `system:infrastructure`, `priority:p0-critical`, `type:task`

### Issue: Player Controller com Joystick Virtual
- **Descrição:** Implementar movimentação do jogador com joystick virtual, câmera top-down e interação por proximidade.
- **Critérios de Aceite:**
  - Jogador se move com joystick virtual (lado esquerdo)
  - Câmera terceira pessoa top-down inclinada
  - Interação contextual por proximidade (auto-prompt)
  - Carry capacity respeitada
- **Dependências:** Setup Projeto Unity 6
- **Estimativa:** 8h
- **Prioridade:** P0
- **Milestone:** MVP
- **Labels:** `system:gameplay`, `priority:p0-critical`, `type:feature`

### Issue: Sistema de Check-in de Clientes
- **Descrição:** Implementar spawn de clientes, registro na recepção e criação de ordem de serviço.
- **Critérios de Aceite:**
  - Cliente spawna conforme taxa configurável (ScriptableObject)
  - Recepção identifica tipo de pet e serviço solicitado
  - Pet entra na fila associada corretamente
  - UI mostra fila e status do atendimento
  - Evento `CustomerArrived` e `PetCheckedIn` disparados
- **Dependências:** Player Controller, Arquitetura Base, Object Pooling
- **Estimativa:** 12h
- **Prioridade:** P0
- **Milestone:** MVP
- **Labels:** `system:gameplay`, `priority:p0-critical`, `type:feature`

### Issue: Estação de Banho
- **Descrição:** Implementar estação de banho funcional com tempo configurável, consumo de shampoo e transição de estado do animal.
- **Critérios de Aceite:**
  - Animal pode ser transportado até estação válida
  - Serviço inicia apenas quando requisitos atendidos (shampoo, operador)
  - Tempo de execução respeita config do animal e upgrades
  - Animal muda para estado "pronto para entrega" ao concluir
  - Eventos `BathStarted` e `BathEnded` disparados
- **Dependências:** Check-in de Clientes, Player Controller
- **Estimativa:** 10h
- **Prioridade:** P0
- **Milestone:** MVP
- **Labels:** `system:gameplay`, `priority:p0-critical`, `type:feature`

### Issue: Sistema de Pagamento no Caixa
- **Descrição:** Implementar caixa que processa pagamento após entrega do pet ao cliente.
- **Critérios de Aceite:**
  - Pagamento só ocorre após entrega correta do pet
  - Valor respeita tabela de serviço e modificadores ativos
  - HUD atualiza Coins imediatamente
  - Evento `PaymentCompleted` com valor registrado para analytics
  - Gorjeta reduzida se atraso > threshold
- **Dependências:** Check-in de Clientes, Estação de Banho, Economia de Coins
- **Estimativa:** 8h
- **Prioridade:** P0
- **Milestone:** MVP
- **Labels:** `system:gameplay`, `system:economy`, `priority:p0-critical`, `type:feature`

### Issue: Economia de Coins e Gems
- **Descrição:** Implementar sistema de moedas dual (Coins + Gems) com transações, feedback e persistência.
- **Critérios de Aceite:**
  - Coins e Gems exibidos em HUD com feedback visual
  - Toda transação gera entrada de analytics
  - Custos por faixa configuráveis via ScriptableObject
  - Não há fontes invisíveis de desconto ou custo
  - Evento `CurrencyChanged` disparado
- **Dependências:** Arquitetura Base, HUD
- **Estimativa:** 8h
- **Prioridade:** P0
- **Milestone:** MVP
- **Labels:** `system:economy`, `priority:p0-critical`, `type:feature`

### Issue: Save/Load Local JSON
- **Descrição:** Implementar persistência local em JSON com versionamento, autosave e fallback.
- **Critérios de Aceite:**
  - Save ocorre em gatilhos críticos e autosave periódico
  - Load restaura moedas, upgrades, funcionários, construções e missões
  - Campo de versão presente no save
  - Fallback para último arquivo válido em caso de corrupção
  - Gravação atômica (temp + replace + checksum)
- **Dependências:** Arquitetura Base
- **Estimativa:** 10h
- **Prioridade:** P0
- **Milestone:** MVP
- **Labels:** `system:save`, `priority:p0-critical`, `type:feature`

### Issue: Sistema de Upgrades
- **Descrição:** Implementar compra de melhorias com custo progressivo e aplicação imediata.
- **Critérios de Aceite:**
  - Cada upgrade possui custo, nível máximo e efeito configuráveis (SO)
  - Custo cresce por curva `C(n) = C0 * (1.18^n)`
  - Efeito aplicado em runtime sem reiniciar cena
  - UI indica benefício incremental antes da compra
  - Evento `UpgradePurchased` disparado
- **Dependências:** Economia de Coins, HUD
- **Estimativa:** 10h
- **Prioridade:** P0
- **Milestone:** MVP
- **Labels:** `system:gameplay`, `system:economy`, `priority:p0-critical`, `type:feature`

### Issue: Contratação de Funcionários
- **Descrição:** Implementar sistema de contratação com custo, roles e persistência.
- **Critérios de Aceite:**
  - Funcionários possuem custo inicial configurável
  - Cada role executa apenas tarefas compatíveis
  - Estado visual e lógico atualizado corretamente
  - Contratação persistida no save
  - Evento `EmployeeHired` disparado
- **Dependências:** Economia, Save, IA State Machine
- **Estimativa:** 8h
- **Prioridade:** P1
- **Milestone:** MVP
- **Labels:** `system:ai`, `priority:p1-high`, `type:feature`

### Issue: IA State Machine de Funcionários
- **Descrição:** Implementar state machine hierárquica com estados Idle/MoveToTask/ExecuteTask/Return/Break.
- **Critérios de Aceite:**
  - Estados implementados com transições determinísticas
  - NavMesh navigation funcional
  - Timeout de navegação reencaminha job
  - Job falho retorna para fila com prioridade aumentada
  - Logs de depuração habilitáveis por ambiente
- **Dependências:** Arquitetura Base, NavMesh setup
- **Estimativa:** 16h
- **Prioridade:** P1
- **Milestone:** MVP
- **Labels:** `system:ai`, `priority:p1-high`, `type:feature`

### Issue: Missões Diárias
- **Descrição:** Implementar sistema de 3 missões diárias com objetivos, tracking e recompensas.
- **Critérios de Aceite:**
  - 3 missões geradas por dia
  - Recompensas incluem Coins, Gems ou boosters
  - Reset em horário configurável
  - Claim entrega recompensa correta e única
  - Eventos de gameplay alimentam tracker automaticamente
- **Dependências:** Economia, Save, Core Loop
- **Estimativa:** 12h
- **Prioridade:** P1
- **Milestone:** Alpha
- **Labels:** `system:retention`, `priority:p1-high`, `type:feature`

### Issue: Receita Offline (Idle Income)
- **Descrição:** Implementar cálculo de receita enquanto jogador está fora do jogo.
- **Critérios de Aceite:**
  - Fórmula: `R_offline = R_tick * ticksValidos * limiteOffline`
  - Efetividade offline: 65% da receita online
  - Cap de 4 horas de acúmulo
  - UI de retorno mostra total ganho e opção de boost (rewarded ad)
  - Validação contra exploits de horário
- **Dependências:** Economia, Save, Funcionários
- **Estimativa:** 10h
- **Prioridade:** P1
- **Milestone:** Alpha
- **Labels:** `system:economy`, `priority:p1-high`, `type:feature`

### Issue: Rewarded Ads
- **Descrição:** Integrar rewarded ads com boost temporário de receita/velocidade.
- **Critérios de Aceite:**
  - Oferta opcional e contextualizada
  - Recompensa entregue apenas após callback válido
  - Cooldowns e limites configuráveis por tipo
  - Eventos de impressão, start e completion enviados
  - Nunca bloqueia ação principal
- **Dependências:** Economia, UI, Core Loop
- **Estimativa:** 8h
- **Prioridade:** P1
- **Milestone:** Alpha
- **Labels:** `system:monetization`, `priority:p1-high`, `type:feature`

### Issue: Object Pooling
- **Descrição:** Implementar sistema de pooling reutilizável para clientes, pets e VFX.
- **Critérios de Aceite:**
  - Pools configuráveis por capacidade inicial e máxima
  - Spawn/despawn sem alocação excessiva em runtime
  - Comportamento transparente para controllers
  - Redução mensurável de GC allocations
- **Dependências:** Arquitetura Base
- **Estimativa:** 8h
- **Prioridade:** P0
- **Milestone:** MVP
- **Labels:** `system:infrastructure`, `priority:p0-critical`, `type:feature`

---

## Subtasks (Exemplo detalhado)

### Feature: Estação de Banho → Subtasks

| # | Subtask | Estimativa |
|---|---------|-----------|
| 1 | Criar `BathStationController` (MonoBehaviour com slots e estado) | 3h |
| 2 | Criar `BathServiceConfig` (ScriptableObject com tempos e custos) | 1h |
| 3 | Implementar UI de progresso da estação (barra + timer) | 2h |
| 4 | Implementar consumo de shampoo do estoque | 1h |
| 5 | Implementar transição de estado do animal (Queued → InService → Ready) | 2h |
| 6 | Disparar eventos `BathStarted` / `BathEnded` | 1h |

### Feature: Save/Load Local → Subtasks

| # | Subtask | Estimativa |
|---|---------|-----------|
| 1 | Criar `SaveData` model com schema versionado | 2h |
| 2 | Criar `ISaveProvider` interface e `LocalJsonProvider` | 3h |
| 3 | Implementar serialização/desserialização JSON | 2h |
| 4 | Implementar gravação atômica (temp → rename → checksum) | 2h |
| 5 | Implementar autosave em gatilhos críticos | 1h |
| 6 | Implementar fallback para backup válido | 2h |
| 7 | Implementar migração de versão de save | 2h |

### Feature: IA State Machine → Subtasks

| # | Subtask | Estimativa |
|---|---------|-----------|
| 1 | Criar `AIStateMachine` base com transições | 3h |
| 2 | Implementar estado `Idle` com consulta de job queue | 2h |
| 3 | Implementar estado `MoveToTask` com NavMesh | 3h |
| 4 | Implementar estado `ExecuteTask` com timer e animação | 3h |
| 5 | Implementar estado `Return` | 1h |
| 6 | Implementar estado `Break` com recuperação | 2h |
| 7 | Criar `JobQueueService` para distribuição de tarefas | 3h |
| 8 | Implementar timeout e requeue de jobs falhos | 2h |

### Feature: Check-in de Clientes → Subtasks

| # | Subtask | Estimativa |
|---|---------|-----------|
| 1 | Criar `CustomerController` com estados (Arriving/Waiting/Served/Paying/Leaving) | 3h |
| 2 | Criar `CustomerSpawnConfig` (ScriptableObject com taxa e tipos) | 1h |
| 3 | Implementar `ReceptionStation` (check-in e criação de ordem) | 3h |
| 4 | Implementar fila por tipo de serviço | 2h |
| 5 | Criar UI de fila (quantidade, próximo da fila) | 2h |
| 6 | Disparar eventos `CustomerArrived`, `PetCheckedIn` | 1h |

### Feature: Economia de Coins e Gems → Subtasks

| # | Subtask | Estimativa |
|---|---------|-----------|
| 1 | Criar `EconomyService` com Coins e Gems | 2h |
| 2 | Criar `TransactionRecord` model para histórico | 1h |
| 3 | Implementar operações Add/Spend/CanAfford | 2h |
| 4 | Integrar com HUD (feedback visual de ganho/gasto) | 2h |
| 5 | Disparar evento `CurrencyChanged` com dados | 1h |
| 6 | Criar `EconomyConfig` SO com custos por faixa | 1h |

---

## Mapa de Dependências

```
┌─────────────────────────────────────────────────────────────────┐
│                    INFRAESTRUTURA (Fundação)                      │
├─────────────────────────────────────────────────────────────────┤
│  Setup Unity 6 → Arquitetura Base → Object Pooling              │
│                         ↓                                        │
│              Player Controller                                   │
└─────────────────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────────────────┐
│                    CORE LOOP (Semana 2)                           │
├─────────────────────────────────────────────────────────────────┤
│  Check-in Clientes → Estação Banho → Entrega → Pagamento       │
│        ↓                   ↓                        ↓            │
│    Sistema Fila      Estação Tosa              Economia          │
│                      Estação Secagem                             │
└─────────────────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────────────────┐
│                 AUTOMAÇÃO (Semana 3)                              │
├─────────────────────────────────────────────────────────────────┤
│  IA State Machine → Contratação → Recepcionista/Banhista        │
│                                        ↓                         │
│                                    Faxineiro                     │
└─────────────────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────────────────┐
│              SAVE + PROGRESSÃO (Semana 3-4)                       │
├─────────────────────────────────────────────────────────────────┤
│  Save/Load → Upgrades → Expansão de Áreas                      │
│                              ↓                                   │
│                    Desbloqueio Espécies                          │
└─────────────────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────────────────┐
│              RETENÇÃO (Semana 4)                                  │
├─────────────────────────────────────────────────────────────────┤
│  Missões Diárias → Conquistas → Login Diário                    │
└─────────────────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────────────────┐
│              MONETIZAÇÃO + IDLE (Semana 5)                        │
├─────────────────────────────────────────────────────────────────┤
│  Idle Income → Rewarded Ads → IAP                               │
│                 Interstitial                                      │
└─────────────────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────────────────┐
│              POLISH + LAUNCH (Semana 5-6)                         │
├─────────────────────────────────────────────────────────────────┤
│  Analytics → Otimização → Audio/VFX → QA → Soft Launch          │
└─────────────────────────────────────────────────────────────────┘
```

---

## Ordem de Implementação (Roadmap)

### Fase 1 - Foundation (Semana 1)
1. Setup Projeto Unity 6 (URP, Input System, Addressables)
2. Arquitetura Base (Managers, Services, Controllers, Data Layer)
3. Player Controller com Joystick Virtual
4. Object Pooling de Entidades
5. Cena Sandbox do Pet Shop (mapa inicial)

### Fase 2 - Core Loop (Semana 2)
6. Check-in de Clientes e Pets
7. Sistema de Fila por Serviço
8. Estação de Banho
9. Entrega e Pagamento no Caixa
10. Economia de Coins e Gems
11. HUD Principal (Moedas, Fila)

### Fase 3 - Automação (Semana 3)
12. IA State Machine de Funcionários
13. Contratação de Funcionários
14. Recepcionista Autônomo
15. Banhista Autônomo
16. Sistema de Upgrades (Jogador e Estações)
17. Save/Load Local JSON

### Fase 4 - Conteúdo MVP (Semana 4)
18. Estação de Tosa
19. Estação de Secagem
20. Expansão de Áreas
21. Desbloqueio de Espécies
22. Faxineiro Autônomo
23. Tela de Upgrades
24. Tela de Loja/Contratação

### Fase 5 - Retenção e Monetização (Semana 5)
25. Missões Diárias e Semanais
26. Login Diário
27. Receita Offline (Idle Income)
28. Rewarded Ads
29. Interstitial Ads
30. Onboarding / FTUE
31. SFX de Ações Principais

### Fase 6 - Polish e Launch (Semana 6)
32. Conquistas
33. IAP (Remove Ads, Starter Pack, Gem Pack)
34. Instrumentação de Analytics
35. Otimização de Performance
36. BGM Loop
37. VFX de Feedback
38. Tela de Missões
39. Tela de Configurações
40. QA Final e Bug Fixes

---

## Próxima Issue Recomendada

> **Setup Projeto Unity 6**
>
> É a fundação de todo o projeto. Sem ela, nenhuma outra issue pode ser iniciada.
> Prioridade: P0 | Milestone: MVP | Estimativa: 4h | Sem dependências.

---

## Resumo Quantitativo

| Métrica | Quantidade |
|---------|-----------|
| Épicos | 9 |
| Features | 40 |
| Issues (detalhadas acima) | 15+ |
| Subtasks (exemplificadas) | 35+ |
| Milestones | 4 |
| Labels | 27 |
| Fases de implementação | 6 |
