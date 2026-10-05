# Produto e objetivos

## Visão

O STOP! substitui papelzinhos, aplicativos genéricos e cronômetros separados por uma única tela que sorteia letras, controla a rodada e registra quais letras já foram usadas.

## Problema

Uma partida presencial de STOP costuma perder ritmo em três momentos:

- escolha manual e potencialmente repetida da letra;
- preparação e acompanhamento do cronômetro;
- dúvida sobre quais letras ainda estão disponíveis.

O produto concentra essas tarefas sem exigir cadastro, internet ou instalação.

## Público

- Grupos de amigos e famílias.
- Professores e mediadores de atividades educativas.
- Organizadores de dinâmicas rápidas em eventos.
- Pessoas que desejam uma ferramenta simples e acessível em qualquer navegador.

## Proposta de valor

> Começar e encerrar uma rodada de STOP com poucos toques, sem repetir letras e sem desviar a atenção do jogo.

## Objetivos do produto

1. Permitir iniciar uma rodada em até 15 segundos após abrir a página.
2. Garantir que nenhuma letra ativa se repita na mesma partida.
3. Comunicar o tempo restante por cor, som e preenchimento visual.
4. Continuar utilizável quando APIs opcionais do navegador não estiverem disponíveis.
5. Preservar privacidade mantendo todos os dados no dispositivo.

## Fora do escopo atual

- Cadastro de jogadores.
- Categorias e respostas dentro da aplicação.
- Pontuação, ranking ou partidas online.
- Sincronização entre dispositivos.
- Backend, conta de usuário ou telemetria.
- Garantia de distribuição uniforme certificada para sorteios oficiais.

## Requisitos funcionais

| ID | Requisito | Critério de aceite |
| --- | --- | --- |
| RF-01 | Sortear uma letra ativa | A letra é retirada do conjunto disponível e marcada na grade |
| RF-02 | Não repetir letras | Uma letra usada só retorna depois de um novo jogo |
| RF-03 | Preparar a rodada | A tela mostra `3`, `2`, `1` antes da letra |
| RF-04 | Controlar o tempo | O preenchimento diminui continuamente até zero |
| RF-05 | Alertar o final | A cor fica amarela em 25% e vermelha em 12% do tempo restante |
| RF-06 | Encerrar manualmente | Tocar ou pressionar Enter/Espaço no cartão ativo encerra a rodada |
| RF-07 | Encerrar automaticamente | O término do tempo produz o mesmo estado final do STOP manual |
| RF-08 | Configurar duração | O usuário escolhe de 5 a 999 segundos |
| RF-09 | Configurar letras | O usuário mantém pelo menos uma das 26 letras ativa |
| RF-10 | Proteger a partida | Letras ficam bloqueadas após o primeiro sorteio |
| RF-11 | Persistir preferências | Tempo e letras permanecem após recarregar a página |
| RF-12 | Reiniciar com segurança | Uma partida com sorteio exige confirmação em dois passos |

## Requisitos não funcionais

| ID | Requisito |
| --- | --- |
| RNF-01 | A aplicação deve funcionar sem backend e sem dependências externas |
| RNF-02 | A tela principal não deve exigir rolagem nas dimensões suportadas |
| RNF-03 | Interações principais devem funcionar por toque, mouse e teclado |
| RNF-04 | Falhas de áudio, vibração, armazenamento ou Wake Lock não devem bloquear o jogo |
| RNF-05 | Dados persistidos devem ser validados antes do uso |
| RNF-06 | A interface deve respeitar a preferência por movimento reduzido |

## Regras de negócio

- O conjunto padrão contém `A` a `Z`.
- A configuração padrão usa 80 segundos.
- O sorteio é aleatório entre as letras ainda disponíveis.
- Alterar o tempo entre rodadas não reinicia o histórico.
- Iniciar um novo jogo mantém a configuração atual.
- Fechar o modal sem salvar descarta as alterações temporárias.

## Princípios de experiência

- **Imediato:** a ação principal deve ser óbvia.
- **Lúdico:** a estética deve lembrar um jogo de mesa, não um painel administrativo.
- **Visível à distância:** a letra e o alerta de STOP dominam a tela.
- **Sem distrações:** nenhum placar, anúncio, login ou navegação paralela.
- **Redundante:** cor, som, vibração e texto se complementam sem depender uns dos outros.

## Indicadores de sucesso

- Fluxo abrir → sortear executado sem erro em navegador suportado.
- Zero repetição até esgotar o conjunto configurado.
- Zero chamada de rede necessária após o carregamento do arquivo.
- Sem rolagem da tela principal nas dimensões da matriz de qualidade.
- Todos os controles interativos identificáveis por tecnologia assistiva.
