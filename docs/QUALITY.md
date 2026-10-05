# Estratégia de qualidade

## Objetivo

Garantir que o ciclo completo — configurar, sortear, jogar, encerrar e reiniciar — funcione sem regressões nos tamanhos de tela suportados.

## Camadas de validação

1. **Sintaxe:** o JavaScript embutido precisa ser compilável.
2. **Estrutura:** não pode haver referência acidental a arquivo ou serviço ausente.
3. **Comportamento:** os fluxos principais devem ser exercitados em navegador real.
4. **Responsividade:** interface e modal devem permanecer utilizáveis nas dimensões de referência.
5. **Acessibilidade:** controles, foco, teclado e mensagens precisam refletir o estado.

## Matriz de visualização

| Perfil | Dimensão | Expectativa |
| --- | --- | --- |
| Celular baixo | `390×667` | Grade compacta e conteúdo principal sem rolagem |
| Celular padrão | `390×844` | Layout vertical completo |
| Celular horizontal | `844×390` | Jogo e configurações em duas colunas |
| Desktop | `1366×768` ou maior | Conteúdo centralizado sem expansão excessiva |

## Casos funcionais mínimos

| ID | Cenário | Resultado esperado |
| --- | --- | --- |
| CT-01 | Abrir a aplicação sem configuração salva | 80 segundos e 26 letras disponíveis |
| CT-02 | Sortear uma letra | Contagem `3, 2, 1`, letra exibida e restante reduzido |
| CT-03 | Tocar na letra durante a rodada | STOP exibido e controles restaurados |
| CT-04 | Deixar o tempo terminar | Mensagem de tempo esgotado e mesmo estado final do STOP |
| CT-05 | Sortear novamente | Nova letra, sem repetir a anterior |
| CT-06 | Tentar abrir configuração durante a rodada | Engrenagem desabilitada |
| CT-07 | Alterar tempo entre rodadas | Novo valor usado na próxima rodada |
| CT-08 | Desmarcar todas as letras | Salvar bloqueado e mensagem de erro exibida |
| CT-09 | Sortear uma letra e abrir configuração | Seleção de letras bloqueada, tempo editável |
| CT-10 | Acionar Novo jogo após sorteio | Primeiro toque pede confirmação e segundo reinicia |
| CT-11 | Recarregar após salvar | Tempo e letras recuperados do `localStorage` |
| CT-12 | Usar Enter ou Espaço no cartão ativo | Rodada encerrada |
| CT-13 | Fechar modal com Escape | Modal fecha e foco retorna à engrenagem |

## Casos de degradação

- Web Audio API indisponível: sorteio continua sem som.
- Vibração indisponível: encerramento continua normalmente.
- Wake Lock negado: cronômetro continua funcionando.
- `localStorage` indisponível: preferências funcionam apenas na sessão atual.
- Aba fica oculta: ao retornar, o tempo considera o período transcorrido.

## Verificação de sintaxe

Com Node.js instalado, a expressão abaixo extrai e compila o script embutido sem executar APIs do navegador:

```powershell
node -e 'const fs=require("fs");const h=fs.readFileSync("index.html","utf8");const s=[...h.matchAll(/<script(?:\s[^>]*)?>([\s\S]*?)<\/script>/gi)];if(s.length!==1)throw new Error("script inesperado");new Function(s[0][1]);console.log("JavaScript válido");'
```

## Checklist antes de publicar

- [ ] CT-01 a CT-13 revisados quando afetados.
- [ ] Console sem erros ou avisos inesperados.
- [ ] Nenhuma URL externa ou segredo adicionado.
- [ ] Layout conferido nas quatro dimensões da matriz.
- [ ] `README.md`, documentação e changelog coerentes com o comportamento.
- [ ] Apenas arquivos intencionais presentes no commit.
