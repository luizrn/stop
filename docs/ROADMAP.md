# Roadmap

O roadmap expressa intenção, não promessa de prazo. Privacidade, simplicidade e confiabilidade têm prioridade sobre quantidade de recursos.

## Entregue — 1.0

- Sorteio sem repetição.
- Contagem regressiva e cronômetro visual.
- STOP manual e automático.
- Configuração de tempo e letras.
- Persistência local.
- Som, vibração e Wake Lock progressivos.
- Layout responsivo vertical e horizontal.
- Interação por toque, mouse e teclado.
- Documentação inicial do produto e engenharia.

## Próximo — 1.1

- Automatizar os fluxos críticos de interface.
- Incluir opção para ativar ou desativar som e vibração.
- Melhorar mensagens para APIs indisponíveis sem poluir a interface.
- Validar contraste e navegação com auditoria automatizada de acessibilidade.

## Futuro — 1.2

- Temas visuais opcionais com contraste equivalente.
- Perfis rápidos de duração por tipo de partida.
- Exportação e importação das preferências em formato simples.
- Indicador opcional de quantidade de rodadas concluídas.

## Em avaliação

- Distribuição como PWA com `manifest`, ícones e service worker completos.
- Modo projetor para telas grandes.
- Internacionalização sem comprometer o arquivo único.

## Não planejado

- Contas, anúncios ou rastreamento.
- Armazenamento de respostas e dados pessoais.
- Ranking online ou partidas multiplayer em tempo real.
- Dependência obrigatória de servidor.

## Critérios para aceitar novos recursos

Uma proposta deve:

- resolver um problema recorrente de uma partida real;
- manter o fluxo principal rápido;
- preservar privacidade e funcionamento local;
- ter fallback quando depender de API opcional;
- incluir critérios de aceite e estratégia de teste;
- justificar qualquer aumento relevante de complexidade.
