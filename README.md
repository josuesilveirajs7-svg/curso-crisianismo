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

Curso completo: 4 trilhas, 48 módulos e 144 aulas. Os temas centrais são tratados em profundidade; os complementares, de forma mais sintética. Informações revisadas em 25/11/2026 (dados de religião do Censo 2022 do IBGE, divulgados em junho de 2025, e relatórios do Pew Research Center de 2025 e 2026).

## Publicar no GitHub Pages

1. Crie um repositório no GitHub (por exemplo, `curso-cristianismo`).
2. Envie os arquivos `index.html` e `README.md` para a raiz do repositório.
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
| `motor` | Navegação, progresso, glossário, busca, tema, linha do tempo, árvore etc. |

Para revisar ou acrescentar conteúdo, edite ou insira um bloco `<script id="conteudo-tX-nY-mZ">` antes do bloco `motor`, usando:

```js
CURSO.modulo('t1-n1-m2', { intro: `...`, aprofundar: { videos: [], leituras: [], livros: [] } });
CURSO.aula('t1-n1-m2-a1', { revisado: 'AAAA-MM-DD', objetivo: '...', secoes: [], exercicio: { p: '...', prompt: '...' } });
```

Os IDs seguem o padrão `t` (trilha) `n` (nível) `m` (módulo) `a` (aula).

## Fontes e neutralidade

O curso separa sempre o que as igrejas ensinam do que a pesquisa histórica afirma, e indica o grau de confiabilidade de cada informação. Os trechos bíblicos vêm da tradução de João Ferreira de Almeida, em sua forma Revista e Corrigida clássica (texto em domínio público). Os vídeos indicados são sempre links de busca no YouTube.
