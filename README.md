# Cristianismo — Da Galileia aos Dias de Hoje

Curso completo, neutro e aprofundado sobre o cristianismo: origens, história, crenças, ramos, práticas e presença no Brasil. Tudo em **uma única página HTML autocontida** (HTML, CSS e JavaScript no mesmo arquivo), em português do Brasil.

Desenvolvido por **Josué Silveira**.

## Estrutura do curso

4 trilhas × 4 níveis (Básico, Intermediário, Avançado, Especialista) × 3 módulos × 3 aulas = **144 aulas**, todas publicadas.

1. **Origens:** Jesus, a Bíblia e os primeiros cristãos
2. **História:** dois mil anos de cristianismo
3. **Ramos e tradições:** catolicismo, ortodoxia e protestantismo
4. **Vida cristã e o cristianismo no Brasil**

Cada aula tem objetivo, explicação em seções, caixas destacadas (conceito-chave, exemplo, analogia, texto bíblico, cuidado, na prática, conexão, dado e fonte), etiquetas de confiabilidade e um exercício com prompt para estudar com o Claude. Cada módulo tem introdução e a seção "Para aprofundar" (vídeos via busca no YouTube, leituras gratuitas e livros).

## Recursos da página

- Abertura animada com logo original em SVG
- Sumário lateral (trilha › nível › módulo › aula), busca e barra de progresso; menu hambúrguer no celular
- Aulas concluídas e tema claro/escuro salvos no navegador (localStorage)
- Botão "Copiar" em todos os prompts de estudo
- Glossário com popover nos termos sublinhados
- Linha do tempo interativa, árvore das igrejas e biblioteca de prompts
- Mobile-first, fonte de 17 px, respeita `prefers-reduced-motion`

## Estado atual

Curso completo: 4 trilhas, 48 módulos e 144 aulas (cerca de 93 mil palavras). Revisão e ampliação de 27/11/2026:

- todas as aulas têm de 4 a 5 seções, com quadros (conceito, exemplo, analogia, Bíblia, cuidado, prática, dado, conexão entre trilhas), perspectivas lado a lado e marcação do grau de certeza (consenso, debate, ensino de igreja, tradição);
- todas as 144 aulas têm quiz de 4 questões, com explicação para cada alternativa;
- todos os exercícios têm prompt de estudo e um critério do que é uma boa resposta;
- glossário ampliado para 91 termos e linha do tempo para 86 eventos; novos prompts gerais.

Dados verificados: religião no Censo 2022 do IBGE (divulgado em junho de 2025), relatórios do Pew Research Center de 2025 e de 18/11/2026, documentos recentes das igrejas.

## Instalar como app

O curso é um app web instalável (PWA). No Chrome do Android, abra o site e toque em ⋮ → **Instalar app** (ou **Adicionar à tela inicial**). No iPhone, use Safari → Compartilhar → **Adicionar à Tela de Início**. Depois de aberto uma vez, funciona também sem internet.

## Arquivos

| Arquivo | Função |
|---|---|
| `index.html` | O curso inteiro (HTML, CSS, JS e conteúdo) |
| `manifest.webmanifest` | Dados do app (nome, cores, ícones) |
| `sw.js` | Service worker: instalação e uso offline |
| `icone-192.png`, `icone-512.png`, `icone-maskable-512.png`, `apple-touch-icon.png` | Ícones do app |
| `README.md` | Esta descrição |

Todos os arquivos ficam na raiz do repositório.

## Publicar no GitHub Pages

1. Crie um repositório no GitHub (por exemplo, `curso-cristianismo`).
2. Envie todos os arquivos para a raiz do repositório.
3. Vá em **Settings → Pages**.
4. Em **Build and deployment**, escolha **Deploy from a branch**, selecione a branch `main` e a pasta `/ (root)` e salve.
5. Em alguns minutos o curso estará em `https://SEU-USUARIO.github.io/curso-cristianismo/`.

Também funciona abrindo o `index.html` direto no navegador, sem servidor.

## Como o código está organizado

O `index.html` tem blocos `<script>` separados, para que cada entrega só **acrescente dados**, sem mexer no motor:

| Bloco | Conteúdo |
|---|---|
| `dados-base` | Objeto `CURSO` e funções de registro |
| `dados-estrutura` | Trilhas, níveis, módulos e títulos das aulas |
| `dados-glossario` | Termos do glossário |
| `dados-linha-do-tempo` | Eventos da linha do tempo |
| `dados-arvore` | Árvore das igrejas |
| `dados-prompts` | Prompts gerais da biblioteca |
| `dados-sobre` | Página "Sobre o curso" |
| `conteudo-tX-nY…` | Conteúdo das aulas, um bloco por nível de cada trilha |
| `complementos-t1-n1` | Quizzes e critérios das aulas longas do Básico da Trilha 1 |
| `dados-ampliados` | Termos, eventos e prompts acrescentados na revisão de 2026 |
| `motor` | Navegação, progresso, glossário, busca, tema, linha do tempo, árvore etc. |

Para revisar ou acrescentar conteúdo, edite ou insira um bloco `<script id="conteudo-tX-nY-mZ">` antes do bloco `motor`, usando:

```js
CURSO.modulo('t1-n1-m2', { intro: `...`, aprofundar: { videos: [], leituras: [], livros: [] } });
CURSO.aula('t1-n1-m2-a1', { revisado: 'AAAA-MM-DD', objetivo: '...', secoes: [{ t: 'Título', h: `<p>…</p>` }],
  quiz: [{ p: 'Pergunta', o: ['A', 'B', 'C', 'D'], c: 1, e: ['por que A', 'por que B', 'por que C', 'por que D'] }],
  exercicio: { p: '...', prompt: '...', criterio: 'O que uma boa resposta deve conter' } });
// acrescentar só quiz e critério a uma aula existente, sem mudar o texto:
CURSO.complemento('t1-n1-m1-a1', { quiz: [...], criterio: '...' });
```

Convenções do HTML das aulas: `<aside data-box="conceito|exemplo|analogia|biblia|cuidado|pratica|conexao|dado" data-t="Título">`, `<span data-tag="consenso|debate|igreja|tradicao|opiniao">`, `<dfn data-g="chave-do-glossario">` e `<div class="persp">` para perspectivas. Citações bíblicas usam a Almeida Revista e Corrigida (domínio público).

Os IDs seguem o padrão `t` (trilha) `n` (nível) `m` (módulo) `a` (aula).

## Fontes e neutralidade

O curso separa sempre o que as igrejas ensinam do que a pesquisa histórica afirma, e indica o grau de confiabilidade de cada informação. Os trechos bíblicos vêm da tradução de João Ferreira de Almeida, em sua forma Revista e Corrigida clássica (texto em domínio público). Os vídeos indicados são sempre links de busca no YouTube.
