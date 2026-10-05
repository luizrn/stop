# Metodologia de desenvolvimento

## Abordagem

O projeto usa uma metodologia enxuta e iterativa, apropriada para uma aplicação pequena e sem backend. Cada ciclo entrega uma mudança observável, validada no navegador e documentada.

## Fluxo de trabalho

```text
Backlog → Pronto → Em desenvolvimento → Revisão → Validação → Concluído
```

| Etapa | Saída esperada |
| --- | --- |
| Backlog | Problema descrito e valor identificado |
| Pronto | Escopo, critérios de aceite e impacto conhecidos |
| Em desenvolvimento | Código e documentação atualizados |
| Revisão | Mudança legível, segura e coerente com a arquitetura |
| Validação | Evidência dos fluxos afetados em navegador real |
| Concluído | Definition of Done atendida e changelog atualizado |

## Planejamento

As prioridades seguem esta ordem:

1. Erros que impedem iniciar ou terminar uma rodada.
2. Acessibilidade, privacidade e segurança.
3. Compatibilidade e responsividade.
4. Clareza da experiência.
5. Novos recursos e refinamentos visuais.

## Definition of Ready

Um item está pronto para desenvolvimento quando:

- explica o problema, não apenas uma solução;
- possui resultado esperado verificável;
- identifica os estados e tamanhos de tela afetados;
- informa se altera dados persistidos;
- cabe em um pull request coeso.

## Implementação

- Preferir APIs nativas e código direto.
- Preservar o requisito de arquivo único, salvo decisão arquitetural aprovada.
- Usar nomes em português no domínio e nomes técnicos convencionais quando apropriado.
- Tratar APIs opcionais com detecção de suporte.
- Evitar estado duplicado e transições implícitas.
- Não introduzir chamada de rede sem necessidade documentada.

## Revisão

A revisão considera:

- correção das regras do jogo;
- consistência da máquina de estados;
- operação por teclado e toque;
- legibilidade e contraste;
- comportamento em telas pequenas;
- tratamento de falhas das APIs do navegador;
- risco de XSS, código dinâmico e recursos externos;
- clareza da documentação.

## Validação

Cada mudança deve executar os casos relacionados de `QUALITY.md`. Alterações de layout exigem pelo menos:

- celular vertical `390×844`;
- celular baixo `390×667`;
- celular horizontal `844×390`.

Mudanças de fluxo exigem inspeção do console sem erros inesperados.

## Definition of Done

- Critérios de aceite atendidos.
- Fluxos afetados testados em navegador real.
- JavaScript sem erro de sintaxe.
- Console sem novos erros ou avisos inesperados.
- Tela principal sem rolagem nas dimensões suportadas.
- Teclado, mouse e toque preservados quando aplicáveis.
- Documentação e changelog atualizados.
- Nenhum artefato temporário incluído no commit.

## Git e versionamento

- Branch principal: `main`.
- Branches curtas: `feat/...`, `fix/...`, `docs/...` ou `chore/...`.
- Commits: Conventional Commits.
- Versões: Semantic Versioning.
- Correção compatível: `PATCH`.
- Recurso compatível: `MINOR`.
- Mudança incompatível: `MAJOR`.

## Releases

1. Confirmar a Definition of Done.
2. Atualizar a seção `Não publicado` do changelog.
3. Definir a nova versão e a data.
4. Criar tag anotada `vX.Y.Z`.
5. Publicar release com resumo e riscos conhecidos.
