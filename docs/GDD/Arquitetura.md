# Arquitetura Unity

Este documento apresenta a arquitetura tecnica do projeto em Unity 6, definindo camadas, responsabilidades de runtime, fluxo de dependencias e criterios de escalabilidade do codigo.

## Visao Arquitetural
Arquitetura em camadas com composicao por servicos e dados em Scriptable Objects para reduzir acoplamento e facilitar balanceamento.

## Camadas
- Presentation Layer: cenas, HUD, telas, animacoes.
- Application Layer: Managers, Services, Controllers.
- Domain Layer: regras de negocio (fila, economia, upgrades, missoes).
- Data Layer: Scriptable Objects, save JSON, configs Addressables.

## Componentes Principais
- Managers: `GameManager`, `UIManager`, `AudioManager`, `SaveManager`, `SpawnManager`.
- Services: `EconomyService`, `MissionService`, `EmployeeService`, `IdleService`, `AdService`, `IAPService`.
- Controllers: `PlayerController`, `StationController`, `CustomerController`, `AIController`.
- Factories: `PetFactory`, `EmployeeFactory`, `UIFactory`.
- Pools: `PetPool`, `CustomerPool`, `VFXPool`.

## Fluxo de Dependencias
Controllers -> Services -> Domain Models -> Data Providers.
Managers coordenam ciclo de vida e bootstrap.

## Estrutura de Pastas Unity
```text
Assets/
  Art/
    Characters/
    Environment/
    Props/
  Audio/
    BGM/
    SFX/
  Materials/
  Prefabs/
    Characters/
    Stations/
    UI/
  Scripts/
    Core/
      Managers/
      Services/
      Controllers/
      Factories/
    Domain/
      Economy/
      Missions/
      Employees/
      Save/
    Data/
      ScriptableObjects/
      Repositories/
    Infrastructure/
      Addressables/
      Pools/
      Analytics/
  UI/
    HUD/
    Screens/
    Widgets/
  Addressables/
    Groups/
  Resources/
    Localization/
```

## Responsabilidades
- Escalar desenvolvimento em equipe sem conflito de ownership.
- Permitir testes de unidade em regras de dominio.

## Dependencias
- [Scriptable Objects](Scriptable_Objects.md)
- [Save System](Save_System.md)
- [Otimizacao](Otimizacao.md)

## Regras de Negocio
- Nenhum controller acessa persistencia diretamente.
- Config de balance deve vir de SO ou config remota, nao hardcoded.

## Eventos
- `BootstrapCompleted`
- `ServiceInitialized`
- `DomainEventPublished`

## Fluxo Operacional
1. Bootstrap de managers.
2. Registro de servicos no container simples (service locator interno).
3. Carga de dados de configuracao.
4. Inicio da simulacao.
