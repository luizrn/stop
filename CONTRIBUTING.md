# Como contribuir

Obrigado por contribuir com o STOP!. O projeto prioriza simplicidade, funcionamento em celulares e ausência de dependências.

## Antes de começar

1. Procure uma issue existente relacionada à mudança.
2. Para alterações maiores, abra uma proposta antes de implementar.
3. Mantenha o escopo de cada pull request pequeno e verificável.
4. Não adicione frameworks ou serviços externos sem uma decisão técnica documentada.

## Ambiente local

Não há instalação de dependências. Use um navegador moderno e, preferencialmente, um servidor local:

```powershell
python -m http.server 4173 --bind 127.0.0.1
```

Abra `http://127.0.0.1:4173`.

## Fluxo de trabalho

1. Crie uma branch a partir de `main`.
2. Faça uma mudança por vez.
3. Atualize a documentação relacionada.
4. Execute a lista de validação em `docs/QUALITY.md`.
5. Abra um pull request usando o modelo do repositório.

## Convenção de commits

Use mensagens curtas no formato Conventional Commits:

```text
feat(timer): adiciona controle de som
fix(settings): impede salvar seleção vazia
docs(readme): documenta execução local
```

Tipos recomendados: `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`.

## Regras técnicas

- Preserve a experiência principal em `index.html`.
- Não envie dados do usuário para serviços externos.
- Use APIs nativas com detecção de suporte e fallback seguro.
- Prefira `textContent` a `innerHTML` para dados dinâmicos.
- Garanta operação por toque, mouse e teclado.
- Respeite `prefers-reduced-motion`.
- Não quebre as dimensões de referência da matriz de testes.

## Definition of Done

Uma mudança está pronta quando:

- atende aos critérios de aceite;
- não apresenta erro ou aviso inesperado no console;
- funciona nos fluxos afetados por toque e teclado;
- mantém a tela principal sem rolagem vertical nos tamanhos suportados;
- inclui documentação e `CHANGELOG.md` quando relevante;
- não introduz dependência ou chamada de rede sem justificativa aprovada.
