# ADR-001 - Arquitetura Base do Projeto

- Status: Aceito

## Contexto
PET SHOP ADMIN exige uma arquitetura que suporte crescimento de escopo, iteração rápida de balanceamento e manutenção por uma equipe multidisciplinar. O projeto combina simulação em tempo real, economia idle, UI com múltiplas telas, persistência local e futura expansão para serviços online.

O risco principal é concentrar lógica em `MonoBehaviours` acoplados, o que dificultaria testes, reuso de dados e escalabilidade de produção.

## Decisao
Adotar arquitetura em camadas com separação entre:

- Presentation Layer para cenas, HUD, widgets, feedback visual e input.
- Application Layer para managers, services, controllers e orquestração.
- Domain Layer para regras de negócio do jogo.
- Data Layer para Scriptable Objects, configurações e save em JSON.

Padrões adotados:

- Managers para ciclo de vida global.
- Services para regras compartilhadas e estado sistêmico.
- Controllers para comportamento de cena e interação com entidades.
- Factories para criação de pets, clientes, funcionários e UI dinâmica.
- Object Pooling para entidades recorrentes.
- Scriptable Objects para configuração de conteúdo e balanceamento.

## Consequencias
Consequências positivas:

- Menor acoplamento entre UI, simulação e persistência.
- Balanceamento iterável sem recompilar lógica central.
- Facilidade para testes de regras críticas, como economia e missões.
- Menor custo para adicionar novas estações, animais e upgrades.

Consequências negativas:

- Exige disciplina de ownership por camada.
- Inicialmente há mais classes e contratos para manter.
- Parte da equipe precisará seguir convenções de injeção e eventos.

## Alternativas Consideradas
- Arquitetura centrada apenas em `MonoBehaviours` por feature.
  - Rejeitada por elevar acoplamento e duplicação de estado.
- Arquitetura ECS completa.
  - Rejeitada para o MVP por custo de implantação e curva da equipe.
- MVC rígido em todas as features.
  - Rejeitada porque services e domain rules oferecem melhor clareza para simulação idle.

## Relacoes
- Documento relacionado: [Arquitetura Unity](../GDD/Arquitetura.md)
- Documento relacionado: [Scriptable Objects](../GDD/Scriptable_Objects.md)
- Documento relacionado: [Save System](../GDD/Save_System.md)# ADR-001 - Arquitetura Base do Projeto

- Status: Aprovado
- Data: 2026-06-02

## Contexto
PET SHOP ADMIN e um jogo mobile de simulacao idle/tycoon com grande volume de entidades simultaneas, multiplos sistemas interdependentes e necessidade de iteracao rapida de balanceamento. O projeto precisa suportar expansoes progressivas de conteudo, integracao futura com analytics remoto, cloud save e live ops sem degradar a manutencao.

O time precisa de uma arquitetura que permita separar regras de negocio de implementacao visual e de infraestrutura, reduzindo acoplamento entre gameplay, economia, persistencia e UI.

## Decisao
Adotar arquitetura em camadas para Unity 6 com os seguintes blocos principais:

- Managers para ciclo de vida, bootstrap e coordenacao global.
- Services para regras de aplicacao e orquestracao de sistemas.
- Controllers para comportamento de cena e interacao com GameObjects.
- Domain Models para regras centrais desacopladas de MonoBehaviour.
- Data Layer baseado em Scriptable Objects para configuracao e balanceamento.
- Infrastructure Layer para save, analytics, ads, IAP, addressables e object pooling.

Principios adotados:

- Controllers nao acessam persistencia diretamente.
- Regras de negocio criticas ficam em classes testaveis fora de MonoBehaviour.
- Configuracoes de balanceamento ficam em Scriptable Objects ou carregamento remoto futuro.
- Comunicacao entre sistemas prioriza eventos de dominio e interfaces simples.

## Consequencias
Positivas:

- Facilita testes unitarios de economia, missoes, progressao e idle income.
- Reduz impacto de alteracoes de UI sobre regras de negocio.
- Permite escalar o projeto para multiplas features sem concentrar tudo em managers gigantes.
- Facilita substituicao futura de providers de ads, IAP, analytics e cloud save.

Negativas:

- Exige disciplina de ownership e convencoes de dependencias.
- Introduz custo inicial maior do que uma arquitetura puramente baseada em MonoBehaviours.
- Demanda documentacao tecnica consistente para evitar duplicacao entre Services e Managers.

## Alternativas Consideradas
- Arquitetura centrada apenas em MonoBehaviours: descartada por alto acoplamento e baixa testabilidade.
- ECS/DOTS desde o inicio: descartada para o MVP por custo de onboarding e complexidade desnecessaria.
- MVC classico para todo o projeto: descartado por inadequacao ao fluxo de cena, spawn e simulacao tipicos de Unity.

## Relacoes
- Baseado em [Arquitetura Unity](../GDD/Arquitetura.md)
- Complementa [ADR-002 - Save System](ADR-002-SaveSystem.md)
- Complementa [ADR-004 - IA](ADR-004-IA.md)