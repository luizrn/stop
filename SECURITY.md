# Política de segurança

## Versões suportadas

| Versão | Suporte |
| --- | --- |
| `main` | Sim |
| Versões anteriores | Não |

## Como relatar uma vulnerabilidade

Não publique detalhes sensíveis em uma issue pública.

1. Acesse a aba **Security** do repositório.
2. Abra um novo aviso privado em **Report a vulnerability**.
3. Informe o impacto, os passos de reprodução e uma correção sugerida, se houver.

O mantenedor buscará confirmar o recebimento em até 7 dias corridos. O prazo de correção dependerá da gravidade e da complexidade.

## Escopo de segurança

O projeto não possui backend, autenticação ou banco de dados. Os principais riscos considerados são:

- execução de scripts externos ou injetados;
- Cross-Site Scripting em manipulações do DOM;
- uso inseguro de conteúdo vindo do `localStorage`;
- abuso de APIs do navegador;
- inclusão acidental de segredos ou telemetria.

## Princípios adotados

- Política de Segurança de Conteúdo no documento.
- Nenhuma dependência ou chamada de rede em tempo de execução.
- Lista permitida de letras e validação estrita do tempo salvo.
- Ausência de `eval`, `new Function` e HTML dinâmico com dados não confiáveis.
- Falhas de áudio, vibração, armazenamento e Wake Lock não interrompem o jogo.
