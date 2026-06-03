# Otimizacao Mobile

Este documento consolida as diretrizes de performance para Android e iOS, detalhando tecnicas, checklists e restricoes necessarias para sustentar o jogo em dispositivos mobile variados.

## Diretrizes Tecnicas
- Object Pooling para NPCs, VFX e objetos de tarefa.
- Occlusion Culling para ambientes internos.
- LOD para props e personagens distantes.
- Texture Atlas para reduzir troca de materiais.
- Addressables para carga sob demanda.
- Controle de draw calls e batches.

## Checklist
- [ ] FPS >= 30 em device alvo minimo.
- [ ] Frame time medio <= 33ms.
- [ ] Draw calls em cena principal <= 180.
- [ ] Memoria RAM pico <= 900MB.
- [ ] Pool warm-up sem stutter perceptivel.
- [ ] Build Android IL2CPP ARM64 validada.
- [ ] Build iOS com metal validada.

## Responsabilidades
- Garantir estabilidade em dispositivos mid/low-end.
- Reduzir consumo de CPU/GPU/bateria.

## Dependencias
- [Arquitetura](Arquitetura.md)
- [Expansao](Expansao.md)

## Regras de Negocio
- Feature nova deve informar custo de performance estimado.
- Sem regressao de FPS acima de 10% por sprint.

## Eventos
- `PerformanceSnapshot`
- `MemoryWarning`
- `AddressableLoaded`

## Fluxo Operacional
1. Profiling em cenas referencia.
2. Aplicar otimizaacoes prioritarias.
3. Revalidar KPI tecnico.
4. Registrar baseline por versao.
