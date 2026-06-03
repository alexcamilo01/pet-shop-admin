# Scriptable Objects

Este documento define os principais Scriptable Objects do projeto e seu papel na configuracao de conteudo, balanceamento, reutilizacao de dados e desacoplamento entre design e codigo.

## AnimalData
- Responsabilidade: definir parametros por especie/tamanho.
- Campos: `id`, `displayName`, `serviceValue`, `serviceTime`, `unlockLevel`, `moodModifiers`.
- Relacionamentos: usado por `PetFactory`, `EconomyService`.

## EmployeeData
- Responsabilidade: definir perfil por cargo.
- Campos: `role`, `baseSpeed`, `efficiency`, `breakInterval`, `upgradeCurve`.
- Relacionamentos: usado por `EmployeeFactory`, `AIController`.

## UpgradeData
- Responsabilidade: catalogo de upgrades.
- Campos: `upgradeId`, `category`, `maxLevel`, `baseCost`, `costFactor`, `effectPerLevel`.
- Relacionamentos: usado por `EconomyService`, `UI upgrades`.

## BuildingData
- Responsabilidade: dados de estacoes e expansoes.
- Campos: `buildingId`, `unlockLevel`, `cost`, `capacity`, `dependencies`.
- Relacionamentos: usado por `StationController`, `ExpansionSystem`.

## MissionData
- Responsabilidade: templates de missao.
- Campos: `missionId`, `type`, `objectiveKey`, `targetValue`, `rewards`, `resetPolicy`.
- Relacionamentos: usado por `MissionService`.

## ItemData
- Responsabilidade: itens de loja e insumos.
- Campos: `itemId`, `category`, `buyCost`, `sellPrice`, `stackLimit`.
- Relacionamentos: usado por `InventoryService`, `ShopSystem`.

## EconomyConfig
- Responsabilidade: parametros globais de economia.
- Campos: `baseTicket`, `spawnRate`, `inflationCurve`, `idleFactor`, `adBoostValues`.
- Relacionamentos: usado por `EconomyService`, `IdleService`.

## BalanceConfig
- Responsabilidade: limites e ranges de balance.
- Campos: `minServiceTime`, `maxServiceTime`, `targetROI`, `offlineCap`, `difficultyBands`.
- Relacionamentos: usado por sistemas de tuning e validacao.

## Responsabilidades
- Centralizar balanceamento fora de codigo.
- Permitir iteracao rapida por design.

## Dependencias
- [Arquitetura](Arquitetura.md)
- [Economia](Economia.md)
- [Upgrades](Upgrades.md)

## Regras de Negocio
- IDs unicos e imutaveis apos release.
- Mudancas de schema requerem migracao de save.

## Eventos
- `SOValidated`
- `SOHotReloaded`

## Fluxo Operacional
1. Carregar colecoes de SO no bootstrap.
2. Validar consistencia de referencias.
3. Disponibilizar para services e factories.
4. Aplicar em runtime via cache.
