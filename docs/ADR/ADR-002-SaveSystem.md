# ADR-002 - Persistencia Local e Save System

- Status: Aceito

## Contexto
O jogo precisa salvar progresso de economia, upgrades, expansões, funcionários, missões e estado mínimo operacional de forma confiável em Android e iOS. O save também precisa permitir futura migração para cloud save sem refazer o contrato de dados.

## Decisao
Adotar persistência local em JSON versionado com snapshots por perfil de jogador. O `SaveManager` será responsável por serialização, versionamento, recuperação e migração leve de schema.

Escopo inicial salvo:

- Coins
- Gems
- Estações desbloqueadas e níveis
- Funcionários contratados e upgrades
- Progresso de missões e conquistas
- Upgrades globais
- Estado de monetização permanente, como remove ads
- Timestamp para cálculo offline

## Consequencias
Consequências positivas:

- Implementação simples e rápida para MVP.
- Fácil inspeção durante QA e balanceamento.
- Compatível com futuras estratégias de cloud sync.

Consequências negativas:

- JSON puro exige cuidado com corrupção de arquivo.
- Necessita versionamento explícito e estratégia de fallback.
- Não é solução anticheat robusta isoladamente.

## Alternativas Consideradas
- PlayerPrefs para todo o save.
  - Rejeitada por fragilidade estrutural e pouca rastreabilidade.
- Banco SQLite local.
  - Rejeitada para MVP por complexidade desnecessária.
- Cloud Save obrigatório desde o início.
  - Rejeitada por aumentar dependências online e custo de desenvolvimento.

## Relacoes
- Documento relacionado: [Save System](../GDD/Save_System.md)
- Documento relacionado: [Idle System](../GDD/Idle_System.md)
- Documento relacionado: [Arquitetura Unity](../GDD/Arquitetura.md)# ADR-002 - Persistencia em JSON com Preparacao para Cloud Save

- Status: Aprovado
- Data: 2026-06-02

## Contexto
O jogo precisa persistir progresso de moedas, upgrades, funcionarios, construcoes, missoes e estado geral da loja de forma confiavel, leve e facil de depurar durante o desenvolvimento. O MVP nao exige cloud save imediato, mas a arquitetura deve permitir evolucao futura sem retrabalho estrutural.

## Decisao
Adotar persistencia local em JSON, serializando um snapshot de progresso agregado por perfil. O sistema sera organizado em:

- `SaveManager` para orquestracao de leitura, escrita e versao.
- `SaveRepository` para acesso ao armazenamento local.
- `SaveData` como objeto agregado raiz.
- `VersionedMigrator` para compatibilidade futura entre versoes.

Diretrizes:

- Autosave em pontos seguros: compra, expansao, fim de missao, retorno do app e intervalos controlados.
- Snapshot unico por perfil com subestruturas para economia, estacoes, funcionarios, upgrades e missoes.
- Preparacao de interface de provider para cloud save futuro sem expor detalhes ao dominio.

## Consequencias
Positivas:

- Implementacao simples e de baixo risco para o MVP.
- Facil depuracao com dumps legiveis durante desenvolvimento.
- Bom alinhamento com dados altamente estruturados e pouco volumosos.
- Facil migracao posterior para provider remoto mantendo o mesmo contrato.

Negativas:

- Necessidade de atencao a corrupcao parcial de arquivo e escrita interrompida.
- Requer versionamento cuidadoso conforme novos sistemas forem adicionados.
- Dados locais podem ser mais expostos a manipulacao em ambientes nao protegidos.

## Alternativas Consideradas
- PlayerPrefs: descartado por inadequacao para dados compostos e versionamento.
- Banco SQLite no MVP: descartado por complexidade superior ao beneficio inicial.
- Cloud save desde o dia 1: descartado por aumentar custo de infraestrutura e integracao antes da validacao do core loop.

## Relacoes
- Baseado em [Save System](../GDD/Save_System.md)
- Relacionado com [Fluxo Save](../Diagramas/Fluxo_Save.md)