# Assets Recomendados para o MVP

## Objetivo
Listar categorias de assets gratuitos recomendados para montar o MVP de PET SHOP ADMIN com coerência visual e baixo risco legal/operacional.

## Diretrizes de Selecao
- Priorizar assets gratuitos com licença compatível para uso comercial.
- Manter coesão low poly cartoon e legibilidade em mobile.
- Evitar dependência de packages abandonados ou sem suporte em Unity 6.

## Categorias Necessarias

### Ambiente
- Kit low poly de interiores comerciais.
- Props de loja, balcões, caixas, prateleiras e divisórias.
- Elementos modulares de piso e parede para expansões.

### Personagens
- Humano estilizado para jogador e clientes.
- Variações simples de NPCs para equipe.
- Pacote de animações básicas: andar, idle, carregar, interagir.

### Pets
- Cachorros pequenos, médios e grandes.
- Gatos.
- Coelhos.
- Hamsters.
- Papagaios.

### UI
- Ícones casuais para moedas, gemas, upgrades e missões.
- Pack de botões, painéis e badges compatíveis com mobile.
- Fonte legível e amigável com suporte a acentuação futura.

### Audio
- Música ambiente leve e repetível.
- SFX para caixa, banho, tosa, clique, recompensa e upgrade.

### VFX
- Partículas simples para limpeza, conclusão de serviço e recompensa.
- Burst visual para upgrade e desbloqueio.

## Estrategia de Curadoria
- Criar planilha interna com fonte, licença, autor e link de cada asset adotado.
- Importar assets em uma cena de validação antes de levá-los ao projeto principal.
- Padronizar materiais e paleta para reduzir sensação de biblioteca heterogênea.

## Responsabilidades
- Artista generalista: curadoria visual e adaptação de materiais.
- Tech artist: revisão de performance, LOD e atlas.
- Produção: rastreio de licença e atribuição, se necessária.

## Dependencias
- [MVP](../GDD/MVP.md)
- [Otimizacao](../GDD/Otimizacao.md)
- [Audio](../GDD/Audio.md)

## Regras de Negocio
- Nenhum asset entra no MVP sem verificação de licença.
- Todo prefab externo deve passar por padronização de escala, material e naming.
- Assets pesados devem ser avaliados para Addressables e pooling quando aplicável.

## Fluxo Operacional
1. Selecionar candidato.
2. Validar licença e compatibilidade.
3. Testar visual e performance.
4. Adaptar materiais e animações.
5. Registrar aprovação no controle interno de assets.# Assets Recomendados para o MVP

## Objetivo
Listar categorias de assets gratuitos e criterios de selecao para construir o MVP de PET SHOP ADMIN com consistencia visual e risco tecnico reduzido.

## Diretrizes de Curadoria
- Priorizar assets gratuitos compativeis com Unity 6 e URP ou facilmente convertiveis.
- Escolher pacotes low poly/cartoon com leitura clara em camera top down inclinada.
- Evitar pacotes com shaders proprietarios pesados ou pipelines legados complexos.
- Preferir assets modulares para ambiente interno de loja.

## Categorias Necessarias

### Ambiente
- Modulos de piso, parede, portas e divisorias internas.
- Balcoes, caixas, prateleiras, mesas de atendimento.
- Props de limpeza, decoracao, iluminacao e sinalizacao.

### Pets e NPCs
- Pacotes low poly de caes, gatos, coelhos, hamsters e aves.
- Humanos stylized para clientes e funcionarios.
- Variacoes simples de cor e acessorios para diversidade visual.

### Estacoes de Trabalho
- Banheira pet, mesa de tosa, secador, comedouros, caixa registradora.
- Gaiolas, camas, recepcao, prateleiras de produtos e area veterinaria.

### UI
- Icones casuais de moedas, gems, upgrades e missoes.
- Pack de botoes, cards, badges e popups mobile friendly.
- Fonte legivel e amigavel com boa leitura em tela pequena.

### Audio
- Musica ambiente casual relaxada.
- SFX de agua, caixa, clique, recompensa, upgrade e celebracao.

## Criterios Tecnicos Obrigatorios
- Texturas compactas e reutilizaveis.
- Numero moderado de materiais por pacote.
- Facilidade de adaptacao para atlas.
- Licenca gratuita compativel com uso comercial.

## Processo de Aprovacao Interno
1. Validar licenca e compatibilidade tecnica.
2. Testar performance em cena de stress.
3. Verificar consistencia de escala, pivot e estilo.
4. Padronizar naming, prefab variants e materiais.

## Riscos
- Mistura excessiva de estilos compromete identidade visual.
- Assets gratuitos podem exigir retrabalho de materiais para URP.
- Animacoes prontas podem nao cobrir todos os loops necessarios.

## Dependencias
- [MVP](../GDD/MVP.md)
- [Arquitetura](../GDD/Arquitetura.md)
- [Otimizacao](../GDD/Otimizacao.md)