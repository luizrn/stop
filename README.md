# STOP!

Sorteador de letras para partidas de **STOP (adedonha)**, feito em um único arquivo HTML, com cronômetro visual, configuração das letras e funcionamento local sem dependências.

## Jogar agora

### [▶ Abrir o STOP! no navegador](https://luizrn.github.io/stop/)

O GitHub não executa JavaScript dentro do README. O link acima abre o mesmo `index.html` publicado pelo GitHub Pages, onde o jogo funciona normalmente.

## Resumo executivo

| Item | Definição |
| --- | --- |
| Propósito | Agilizar o sorteio de letras e controlar o tempo de cada rodada de STOP |
| Público | Famílias, escolas, grupos de amigos e mediadores de atividades |
| Plataforma | Navegadores modernos em celular, tablet e desktop |
| Entrega | Aplicação estática e autônoma em `index.html` |
| Jogo online | [luizrn.github.io/stop](https://luizrn.github.io/stop/) |
| Estado | Versão inicial funcional e validada |
| Idioma | Português do Brasil |

## O que funciona

- Sorteio sem repetição entre as letras habilitadas.
- Contagem regressiva de 3 segundos antes de cada rodada.
- Cronômetro visual que esvazia e muda para amarelo e vermelho no final.
- Encerramento por toque na letra ou automaticamente quando o tempo acaba.
- Avisos sonoros nos últimos 10 segundos, vibração e tentativa de manter a tela acesa.
- Configuração de 5 a 999 segundos e seleção individual das letras.
- Persistência das configurações no `localStorage`.
- Confirmação em dois passos antes de zerar uma partida em andamento.
- Layout responsivo, acessível por teclado e sem rolagem na tela principal.

## Objetivos

1. Reduzir o tempo gasto organizando cada rodada.
2. Evitar letras repetidas durante a mesma partida.
3. Tornar o cronômetro legível sem exibir números durante a rodada.
4. Funcionar bem em celulares, inclusive na horizontal e em telas baixas.
5. Permanecer simples de abrir, compartilhar, auditar e manter.

Os requisitos completos e os critérios de sucesso estão em [Produto e objetivos](docs/PRODUCT.md).

## Tecnologias

| Tecnologia | Uso |
| --- | --- |
| HTML5 | Estrutura semântica e acessibilidade |
| CSS3 | Design responsivo, animações e cronômetro visual |
| JavaScript | Estado do jogo, sorteio, temporizadores e configurações |
| Web Audio API | Contagem, alertas e som de STOP sintetizado |
| Screen Wake Lock API | Tentativa de manter a tela ligada durante a rodada |
| Vibration API | Retorno tátil em dispositivos compatíveis |
| Web Storage API | Persistência local das configurações |

Não há framework, processo de build, pacote npm, backend, banco de dados ou serviço externo.

## Como executar

### Opção rápida

Abra o arquivo `index.html` diretamente no navegador.

### Servidor local

Algumas APIs do navegador funcionam melhor em uma origem HTTP local:

```powershell
python -m http.server 4173 --bind 127.0.0.1
```

Acesse `http://127.0.0.1:4173`.

## Como jogar

1. Abra as configurações, escolha o tempo e as letras, e salve.
2. Pressione **Sortear letra** e aguarde a contagem `3, 2, 1`.
3. Preencha as categorias combinadas pelo grupo.
4. Toque no cartão da letra quando alguém terminar; o tempo esgotado também encerra a rodada.
5. Sorteie novamente ou use **Novo jogo** para restaurar todas as letras configuradas.

## Regras implementadas

- O tempo mínimo é 5 segundos e o máximo é 999 segundos.
- Pelo menos uma letra deve permanecer habilitada.
- As letras podem ser alteradas somente antes do primeiro sorteio da partida.
- O tempo pode ser alterado entre rodadas.
- A engrenagem fica indisponível durante a contagem e a rodada.
- Uma letra sorteada não volta ao conjunto disponível até o início de um novo jogo.
- Um novo jogo mantém o tempo e as letras configuradas.

## Arquitetura

O projeto usa uma arquitetura monolítica estática deliberada:

```text
index.html
├── metadados e política de segurança
├── estilos e responsividade
├── interface do jogo e configurações
└── regras, estado, áudio e integrações com o navegador
```

O estado principal possui três fases: `idle`, `countdown` e `running`. Não existem chamadas de rede nem dados enviados para servidores. Consulte [Arquitetura](docs/ARCHITECTURE.md) para fluxos, decisões e modelo de persistência.

## Metodologia

O desenvolvimento segue ciclos curtos orientados a comportamento:

1. Definir uma mudança pequena e seus critérios de aceite.
2. Implementar preservando a aplicação em arquivo único.
3. Verificar sintaxe e segurança básica.
4. Testar os fluxos reais em diferentes dimensões de tela.
5. Registrar a alteração e atualizar a documentação.

O processo completo, Definition of Ready e Definition of Done estão em [Metodologia](docs/METHODOLOGY.md).

## Qualidade e segurança

- JavaScript verificado por análise de sintaxe.
- Fluxos principais exercitados em navegador real com Playwright.
- Layout validado em `390×667`, `390×844` e `844×390`.
- Manipulação de texto com `textContent`, sem avaliação dinâmica de código.
- Content Security Policy declarada no próprio documento.
- Configuração salva é validada e filtrada antes do uso.
- Aplicação sem scripts, fontes ou serviços externos.

O plano reproduzível está em [Qualidade](docs/QUALITY.md). Vulnerabilidades devem seguir o processo descrito em [Segurança](SECURITY.md).

## Estrutura do repositório

```text
.
├── .github/                 # Modelos de issues e pull requests
├── docs/                    # Produto, arquitetura, processo, qualidade e roadmap
├── index.html               # Aplicação completa
├── CHANGELOG.md             # Histórico de versões
├── CODE_OF_CONDUCT.md       # Regras de convivência
├── CONTRIBUTING.md          # Guia de contribuição
├── README.md                # Visão geral
└── SECURITY.md              # Política de segurança
```

## Documentação

- [Produto, objetivos e requisitos](docs/PRODUCT.md)
- [Arquitetura e decisões técnicas](docs/ARCHITECTURE.md)
- [Metodologia de desenvolvimento](docs/METHODOLOGY.md)
- [Estratégia de qualidade](docs/QUALITY.md)
- [Roadmap](docs/ROADMAP.md)
- [Como contribuir](CONTRIBUTING.md)
- [Histórico de mudanças](CHANGELOG.md)

## Roadmap resumido

- Melhorar os testes automatizados de interface.
- Adicionar opção de som e vibração nas configurações.
- Avaliar distribuição como PWA sem comprometer o modo de arquivo único.
- Adicionar temas visuais mantendo contraste e legibilidade.

Veja prioridades, limites e critérios em [Roadmap](docs/ROADMAP.md).

## Contribuição

Contribuições são bem-vindas por issues e pull requests. Antes de começar, leia [CONTRIBUTING.md](CONTRIBUTING.md) e o [Código de Conduta](CODE_OF_CONDUCT.md).

## Licença

Nenhuma licença de código aberto foi definida. A publicação deste repositório não concede automaticamente permissão para copiar, modificar ou redistribuir o código. Uma licença poderá ser adicionada quando o mantenedor escolher seus termos.
