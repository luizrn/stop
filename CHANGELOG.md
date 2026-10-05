# Histórico de mudanças

Todas as mudanças relevantes deste projeto serão registradas neste arquivo. O formato segue os princípios de [Keep a Changelog](https://keepachangelog.com/pt-BR/1.1.0/) e o versionamento seguirá [Semantic Versioning](https://semver.org/lang/pt-BR/).

## [Não publicado]

### Planejado

- Ampliar a automação dos testes de interface.
- Avaliar controles para som e vibração.

## [1.0.0] - 2026-10-05

### Adicionado

- Sorteio de letras sem repetição.
- Contagem regressiva e cronômetro visual.
- Encerramento manual e automático da rodada.
- Configuração de tempo e letras com persistência local.
- Alertas sonoros, vibração e integração com Wake Lock.
- Confirmação para iniciar um novo jogo.
- Design responsivo para celular vertical, celular horizontal e desktop.
- Navegação por teclado, gerenciamento de foco e informações acessíveis.
- Política de segurança de conteúdo e favicon embutido.

### Corrigido

- Remoção de scripts injetados e referências a recursos inexistentes.
- Tratamento seguro para navegadores sem suporte à Web Audio API.
- Estados inconsistentes entre contagem, rodada e configurações.
- Controles de letras visíveis quando deveriam permanecer bloqueados.
- Arraste das rodas numéricas com mouse.
