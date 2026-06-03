# Save System

Este documento define a persistencia de progresso de PET SHOP ADMIN, cobrindo escopo dos dados salvos, gatilhos de gravacao, recuperacao de estado e preparacao para cloud save futuro.

## Escopo de Persistencia
Salvar obrigatoriamente:
- Coins
- Gems
- Funcionarios
- Upgrades
- Construcoes/Expansoes
- Missoes e conquistas

## Tecnologia
- JSON local com versao de schema.
- Persistencia em `Application.persistentDataPath`.

## Estrutura de Dados (resumo)
```json
{
  "saveVersion": 1,
  "currencies": { "coins": 0, "gems": 0 },
  "employees": [],
  "upgrades": [],
  "buildings": [],
  "missions": [],
  "timestampUtc": "2026-06-02T00:00:00Z"
}
```

## Cloud Save Futuro
- Abstracao via `ISaveProvider`.
- Providers: LocalJsonProvider (MVP), CloudProvider (futuro).
- Politica de conflito: maior progresso por timestamp + checksum.

## Responsabilidades
- Garantir integridade e recuperacao de progresso.
- Suportar migracao de versoes de save.

## Dependencias
- [Arquitetura](Arquitetura.md)
- [Idle System](Idle_System.md)
- [Economia](Economia.md)

## Regras de Negocio
- Autosave em eventos criticos e ao sair da sessao.
- Backup rotativo com ultimo save valido.

## Eventos
- `SaveRequested`
- `SaveCompleted`
- `LoadCompleted`
- `SaveCorruptedDetected`

## Fluxo Operacional
1. Coletar estado dos agregados de dominio.
2. Serializar para JSON.
3. Gravar atomico (temp + replace).
4. Confirmar checksum.
5. Disponibilizar para carga futura.
