# Audio

Este documento define a direcao de audio do projeto, incluindo musica ambiente, efeitos sonoros e principios de feedback auditivo para reforcar clareza, recompensa e atmosfera casual.

## Escopo
- Musica ambiente por area.
- SFX de banho.
- SFX de caixa/pagamento.
- SFX de upgrade.
- SFX de recompensa.

## Direcao de Audio
- Estilo leve, amigavel, energetico.
- Camadas dinamicas por intensidade de fila.

## Responsabilidades
- Reforcar feedback de progresso e satisfacao.
- Melhorar legibilidade de eventos sem depender apenas da UI.

## Dependencias
- [Gameplay](Gameplay.md)
- [UI UX](UI_UX.md)

## Regras de Negocio
- Ducking de musica durante recompensas importantes.
- Limite de vozes simultaneas para evitar clipping em mobile.

## Eventos
- `BGMChanged`
- `SFXPlayed`
- `AudioSettingsUpdated`

## Fluxo Operacional
1. Sistema de audio assina eventos de jogo.
2. Seleciona clip por contexto.
3. Reproduz em mixer group adequado.
4. Ajusta volume por configuracao do usuario.
