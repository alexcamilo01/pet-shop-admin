# MVP

Este documento delimita o escopo minimo viavel de PET SHOP ADMIN, separando o que precisa existir para validar o produto do que deve permanecer reservado para versoes futuras.

## Inclui no MVP
- Loop principal completo (check-in -> servico -> entrega -> pagamento).
- Estacoes: Recepcao, Banho, Tosa, Caixa.
- Animais base: cachorro pequeno/medio, gato, hamster.
- 4 cargos de funcionario: recepcionista, banhista, tosador, faxineiro.
- Upgrades essenciais (velocidade, capacidade, valor de servico).
- Save local JSON.
- Ads rewarded e interstitial basico.
- Missoes diarias simples.

## Fica para Versoes Futuras
- Hotel para pets completo.
- Clinica veterinaria e tratamentos premium.
- Eventos sazonais avancados.
- Cloud save e social features.
- Sistema VIP expandido.

## Politica de Assets
- Uso exclusivo de assets gratuitos na fase MVP.
- Curadoria em [Assets Recomendados](../Assets/Assets_Recomendados.md).

## Responsabilidades
- Entregar versao jogavel e mensuravel para soft launch.
- Validar retencao e funil de monetizacao inicial.

## Dependencias
- [Roadmap](../Roadmap/Roadmap.md)
- [Backlog Inicial](../Backlog/Backlog_Inicial.md)

## Regras de Negocio
- MVP deve ser completo em loop, nao em quantidade de conteudo.
- Toda feature de MVP precisa telemetria associada.

## Eventos
- `MVPFeatureEnabled`
- `SoftLaunchMetricsCollected`

## Fluxo Operacional
1. Congelar escopo MVP.
2. Implementar features core.
3. Testar em cohort fechado.
4. Ajustar balance e UX.
5. Preparar soft launch.
