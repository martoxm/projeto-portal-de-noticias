# Documentação de Estudo — Projeto Portal de Notícias

> **Repositório:** [https://github.com/martoxm/projeto-portal-de-noticias](https://github.com/martoxm/projeto-portal-de-noticias)
> **Tecnologias:** HTML5 · CSS3 (CSS Nesting · CSS Grid · Custom Properties)
> **Objetivo do projeto:** Construir uma página estática de portal de notícias aplicando boas práticas de estruturação HTML semântica, CSS modular, sistema de design com variáveis e classes utilitárias.

***

## Índice

1. [Estrutura Final do Projeto](#estrutura-final-do-projeto)
2. [Histórico de Commits (ordem cronológica)](#histórico-de-commits-ordem-cronológica)
   - [Commit 1 — Iniciando o projeto](#commit-1--iniciando-o-projeto)
   - [Commit 2 — Adicionando .gitignore](#commit-2--adicionando-gitignore)
   - [Commit 3 — Editando .gitignore](#commit-3--editando-gitignore)
   - [Commit 4 — Adicionando variáveis de cores](#commit-4--adicionando-variáveis-de-cores)
   - [Commit 5 — Aplicando fonte no projeto](#commit-5--aplicando-fonte-no-projeto)
   - [Commit 6 — Organizando os assets](#commit-6--organizando-os-assets)
   - [Commit 7 — Criando o header](#commit-7--criando-o-header)
   - [Commit 8 — Ajuste de espaço entre itens do menu](#commit-8--ajuste-de-espaço-entre-itens-do-menu)
   - [Commit 9 — Estruturando a seção Destaques](#commit-9--estruturando-a-seção-destaques)
   - [Commit 10 — Adicionando fundo com degradê](#commit-10--adicionando-fundo-com-degradê)
   - [Commit 11 — Ajustando o conteúdo do card](#commit-11--ajustando-o-conteúdo-do-card)
   - [Commit 12 — Finalizando a seção Destaques](#commit-12--finalizando-a-seção-destaques)
   - [Commit 13 — Estruturando "Mais lidas da semana"](#commit-13--estruturando-mais-lidas-da-semana)
   - [Commit 14 — Estilizando "Mais lidas da semana"](#commit-14--estilizando-mais-lidas-da-semana)
   - [Commit 15 — Estruturando as últimas seções](#commit-15--estruturando-as-últimas-seções)
   - [Commit 16 — Estilizando os últimos cards](#commit-16--estilizando-os-últimos-cards)
   - [Commit 17 — Hover nos botões do header](#commit-17--hover-nos-botões-do-header)
   - [Commits 18–25 — Documentação (README)](#commits-1825--documentação-readme)
3. [Conceitos Aplicados no Projeto](#conceitos-aplicados-no-projeto)
   - [CSS Custom Properties (Variáveis)](#css-custom-properties-variáveis)
   - [CSS Grid Layout](#css-grid-layout)
   - [CSS Nesting](#css-nesting)
   - [CSS Utility-First](#css-utility-first)
   - [HTML Semântico](#html-semântico)
   - [CSS Pseudo-elementos](#css-pseudo-elementos)
4. [Arquitetura de Arquivos CSS](#arquitetura-de-arquivos-css)

***

## Estrutura Final do Projeto

```
projeto-portal-de-noticias/
├── .gitignore
├── .vscode/
├── README.md
├── index.html
├── assets/
│   ├── Logo.svg
│   ├── icons/
│   │   ├── List.svg
│   │   ├── MagnifyingGlass.svg
│   │   ├── ArrowRight.svg
│   │   └── ArrowRight-hover.svg
│   └── images/
│       ├── Image 01.png → Image 18.png
│       └── Ads.png
└── style/
    ├── index.css        ← arquivo raiz, importa os demais
    ├── global.css       ← reset, variáveis, estilos base
    ├── utility.css      ← classes utilitárias (grid, gap, text)
    ├── header.css       ← estilos do header
    └── sections.css     ← estilos das seções do main
```

***

## Histórico de Commits (ordem cronológica)

### Commit 1 — Iniciando o projeto

**SHA:** `19763896`  
**Data:** 07/06/2026 — 19:32

#### O que foi feito

Criação dos arquivos base do projeto: `index.html`, pasta `style/` e os primeiros arquivos CSS.

#### Estrutura HTML base criada

```html
<!doctype html>
<html lang="pt-br">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="style/index.css" />
    <title>Portal de notícias</title>
  </head>
  <body>
    <!-- conteúdo será adicionado nos commits seguintes -->
  </body>
</html>
```

#### Conceito: `lang="pt-br"`

Define o idioma do documento para português do Brasil. Importante para acessibilidade (leitores de tela) e SEO.

#### Conceito: `<meta name="viewport">`

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

Garante que o layout se adapte corretamente em dispositivos móveis, definindo a largura da viewport igual à largura da tela do dispositivo.

***

### Commit 2 — Adicionando .gitignore

**SHA:** `37813688`  
**Data:** 07/06/2026 — 19:34

#### O que foi feito

Criação do arquivo `.gitignore` para evitar que arquivos desnecessários (como configurações locais de editor) sejam rastreados pelo Git.

#### Conceito: `.gitignore`

O `.gitignore` lista padrões de arquivos e pastas que o Git deve ignorar. No contexto deste projeto, o arquivo ignorou a pasta `.vscode/` com as configurações locais do Visual Studio Code.

```
.vscode/
```

> **Por que ignorar `.vscode/`?** As configurações de editor são pessoais e específicas da máquina de cada desenvolvedor. Incluí-las no repositório pode gerar conflitos desnecessários para outras pessoas que clonarem o projeto.

***

### Commit 3 — Editando .gitignore

**SHA:** `3da85216`  
**Data:** 07/06/2026 — 19:34

#### O que foi feito

Ajuste fino no `.gitignore` após o primeiro commit. Refinamento de alguma entrada ou adição de novo padrão.

> **Lição de Git:** É comum editar o `.gitignore` logo após criá-lo quando percebemos que algum arquivo já rastreado precisa ser ignorado ou que o padrão estava incorreto.

***

### Commit 4 — Adicionando variáveis de cores

**SHA:** `4e7a9816`  
**Data:** 07/06/2026 — 19:41

#### O que foi feito

Criação de `style/global.css` com o reset CSS e a definição do sistema de design através de **CSS Custom Properties** no seletor `:root`.

#### Código — `style/global.css` (variáveis)

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

:root {
  --brand-color-light: #60a5fa;
  --brand-color-dark: #1d4ed8;
  --bg-color: #0f172a;
  --stroke-color: #1e293b;
  --text-color-primary: #f1f5f9;
  --text-color-secondary: #cbd5e1;
}
```

#### Conceito: CSS Custom Properties (Variáveis CSS)

Variáveis CSS são definidas com o prefixo `--` e utilizadas com a função `var()`. Ao centralizar as cores no `:root`, qualquer alteração no sistema de cores do projeto requer mudança em apenas um lugar.

```css
/* Definição */
:root {
  --brand-color-dark: #1d4ed8;
}

/* Uso */
.content-tag {
  background-color: var(--brand-color-dark);
}
```

#### Conceito: Reset CSS com `box-sizing: border-box`

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

```

- `margin: 0` e `padding: 0` removem os espaçamentos padrão do navegador.
- `box-sizing: border-box` faz com que `padding` e `border` sejam incluídos dentro da `width` e `height` do elemento, tornando o cálculo de layout muito mais previsível.

***

### Commit 5 — Aplicando fonte no projeto

**SHA:** `27f8fd36`  
**Data:** 07/06/2026 — 19:52

#### O que foi feito

Integração da fonte **Archivo** (do Google Fonts) e criação das variáveis tipográficas usando a shorthand `font`.

#### Código — Variáveis de tipografia em `global.css`

```css
:root {
  /* ... cores anteriores ... */

  --font-family: "Archivo", sans-serif;
  --h1: 800 24px/135% var(--font-family);
  --h2: 800 16px/140% var(--font-family);
  --h3: 800 14px/140% var(--font-family);
  --text-span: 600 14px/140% var(--font-family);
  --text: 400 16px/140% var(--font-family);
  --text-sm: 400 14px/160% var(--font-family);
}

body {
  font: var(--text);
  color: var(--text-color-primary);
  background-color: var(--bg-color);
}
```

#### Código — Importação no `index.html`

```html
<head>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link
    href="https://fonts.googleapis.com/css2?family=Alice&family=Archivo:ital,wght@0,100..900;1,100..900&family=Inter:ital,opsz@0,14..32;1,14..32&family=Poppins:wght@400;700&display=swap"
    rel="stylesheet"
  />
</head>
```

#### Conceito: Shorthand `font`

A propriedade `font` é uma shorthand que aceita: `font-style font-variant font-weight font-size/line-height font-family`.

```css
/* Equivalente a: */
font-weight: 800;
font-size: 24px;
line-height: 135%;
font-family: "Archivo", sans-serif;

/* Shorthand: */
font: 800 24px/135% "Archivo", sans-serif;
```

#### Conceito: `<link rel="preconnect">`

Instrui o navegador a estabelecer antecipadamente a conexão com o servidor do Google Fonts, reduzindo a latência no carregamento das fontes.

***

### Commit 6 — Organizando os assets

**SHA:** `423449de`  
**Data:** 07/06/2026 — 19:59

#### O que foi feito

Organização da pasta `assets/` com subpastas `icons/` e `images/`, adicionando as imagens e ícones SVG que serão utilizados no projeto.

#### Estrutura de assets

```
assets/
├── Logo.svg                  ← logotipo do portal "TechNews"
├── icons/
│   ├── List.svg              ← ícone hamburguer do menu
│   ├── MagnifyingGlass.svg   ← ícone de busca
│   ├── ArrowRight.svg        ← seta dos links "Ver tudo"
│   └── ArrowRight-hover.svg  ← versão hover da seta
└── images/
    ├── Image 01.png          ← imagem hero (card principal)
    ├── Image 02.png → 18.png ← imagens dos cards de notícias
    └── Ads.png               ← imagem de anúncio (aside)
```

> **Boas práticas:** Separar assets em subpastas (`icons/`, `images/`) facilita a manutenção e a escalabilidade do projeto. Ícones SVG são preferidos por serem vetoriais (escalam sem perda de qualidade) e terem arquivos menores.

***

### Commit 7 — Criando o header

**SHA:** `dfca4e98`  
**Data:** 07/06/2026 — 20:17

#### O que foi feito

Criação da estrutura HTML do `<header>` com dois `<nav>`: o primário (logo + menu hamburguer + busca) e o secundário (categorias de notícias).

#### Código HTML — Header

```html
<header class="container">
  <!-- Nav primário: menu | logo | busca -->
  <nav id="primary" class="grid grid-flow-col">
    <div>
      <img src="./assets/icons/List.svg" alt="ícone de menu" />
      <strong>Menu</strong>
    </div>
    <div>
      <img src="./assets/Logo.svg" alt="TechNews logo" />
    </div>
    <div>
      <strong>Buscar</strong>
      <img src="./assets/icons/MagnifyingGlass.svg" alt="ícone de lupa para pesquisa" />
    </div>
  </nav>

  <!-- Nav secundário: categorias -->
  <nav id="secondary" class="grid grid-flow-col">
    <a href="#">Inteligência Artificial</a>
    <a href="#">Blockchain</a>
    <a href="#">Hologramas</a>
    <a href="#">Internet</a>
    <a href="#">Vestíveis</a>
    <a href="#">Realidade Aumentada</a>
    <a href="#">Realidade Virtual</a>
  </nav>
</header>
```

#### Código CSS — `style/header.css`

```css
#primary {
  padding-block: 20px;

  div {
    display: flex;
    align-items: center;
    gap: 8px;
  }
  /* nesting css */

  div:nth-child(2) {
    margin-inline: auto; /* centraliza o logo */
  }

  div:nth-child(3) {
    justify-self: end; /* empurra o botão de busca para a direita */
  }
}

#secondary {
  padding-block: 14px;
  border: solid 1px var(--stroke-color);
  border-inline: none; /* borda apenas em cima e em baixo */
  justify-content: space-between;
}
```

#### Conceito: Propriedades lógicas CSS (`padding-block`, `margin-inline`, `border-inline`)

As propriedades lógicas substituem as direcionais (`top/right/bottom/left`) por equivalentes baseados no fluxo do texto:

| Propriedade lógica | Equivalente direcional |
|---|---|
| `padding-block` | `padding-top` + `padding-bottom` |
| `padding-inline` | `padding-left` + `padding-right` |
| `margin-inline: auto` | `margin-left: auto; margin-right: auto` |
| `border-inline: none` | `border-left: none; border-right: none` |

Usar propriedades lógicas é uma boa prática pois suporta melhor idiomas com escrita vertical ou da direita para esquerda (RTL).

#### Conceito: `justify-self: end` no CSS Grid

No grid, `justify-self` controla o alinhamento horizontal de um item individual dentro de sua célula. O valor `end` o empurra para o lado direito, sem tirar os outros itens do lugar.

***

### Commit 8 — Ajuste de espaço entre itens do menu

**SHA:** `1d457731`  
**Data:** 07/06/2026 — 20:17

#### O que foi feito

Ajuste no `#secondary` para distribuir os links de categoria igualmente com `justify-content: space-between` (já presente no commit anterior como refinamento de espaçamento).

> Este commit demonstra o processo iterativo de desenvolvimento: você estrutura, visualiza no browser, ajusta os detalhes e comita a melhoria.

***

### Commit 9 — Estruturando a seção Destaques

**SHA:** `98fc5fe9`  
**Data:** 07/06/2026 — 20:32

#### O que foi feito

Criação da estrutura HTML da seção `#featured` (Destaques), que exibe um card principal grande e 4 cards menores em grid.

#### Código HTML — Seção `#featured`

```html
<main class="grid container">
  <section id="featured" class="grid grid-flow-col gap-16">
    <!-- Card principal (grande) -->
    <figure class="card">
      <img src="assets/images/Image 01.png" alt="" />
      <figcaption>
        <span class="content-tag">Robótica</span>
        <h2 class="text-2xl">
          Robôs domésticos começam a ser adotados para tarefas diárias,
          prometendo mais conforto e eficiência nas residências.
        </h2>
      </figcaption>
    </figure>

    <!-- Grid 2x2 com 4 cards menores -->
    <div class="grid grid-cols-2 gap-16">
      <figure class="card">
        <img src="assets/images/Image 02.png" alt="..." />
        <figcaption>
          <span class="content-tag">Hologramas</span>
          <h2 class="text-lg">Novo Smartphone Projetor 3D chega ao mercado...</h2>
        </figcaption>
      </figure>
      <!-- ... 3 cards adicionais com a mesma estrutura -->
    </div>
  </section>
</main>
```

#### Conceito: `<figure>` e `<figcaption>`

`<figure>` é um elemento semântico que representa conteúdo autocontido (imagem, diagrama, código). `<figcaption>` fornece uma legenda para esse conteúdo. Usar esses elementos em vez de `<div>` + `<p>` melhora a semântica e a acessibilidade.

#### CSS inicial de `#featured` em `sections.css`

```css
#featured {
  grid-area: featured;
  img {
    height: 100%;
    object-fit: cover;
  }
}
```

#### Conceito: `object-fit: cover`

Faz a imagem preencher completamente o container sem distorção, recortando as bordas se necessário. É o equivalente CSS de `background-size: cover` para imagens `<img>`.

***

### Commit 10 — Adicionando fundo com degradê

**SHA:** `12a70fea`  
**Data:** 07/06/2026 — 20:39

#### O que foi feito

Adição do gradiente escuro sobre as imagens dos cards de destaque, usando o **pseudo-elemento `::before`**, para garantir legibilidade do texto sobre a imagem.

#### Código CSS — Degradê com `::before`

```css
#featured {
  .card {
    border-radius: 4px;
    overflow: hidden;
    position: relative;

    &::before {
      content: "";
      position: absolute;
      inset: 0;
      top: 50%;
      background: linear-gradient(180deg, transparent 0%, #020617 100%);
    }
  }
}
```

#### Conceito: Pseudo-elemento `::before` para overlay

O pseudo-elemento `::before` cria um elemento filho virtual posicionado antes do conteúdo do elemento pai. Aqui ele é usado para criar uma sobreposição (overlay) gradiente sem adicionar HTML desnecessário.

**Por que `position: relative` no `.card` e `position: absolute` no `::before`?**
- O pai com `position: relative` se torna o contexto de posicionamento.
- O `::before` com `position: absolute` + `inset: 0` se estica para cobrir todo o pai.
- `inset: 0` é equivalente a `top: 0; right: 0; bottom: 0; left: 0`.
- `top: 50%` sobrescreve o `inset: 0` para o topo, fazendo o gradiente começar a partir da metade da imagem.

```css
/* inset: 0 → cobre todo o card */
/* top: 50% → começa o gradiente apenas a partir da metade */
inset: 0;
top: 50%;
```

#### Conceito: `linear-gradient`

```css
background: linear-gradient(180deg, transparent 0%, #020617 100%);
```

Cria um gradiente de cima para baixo (`180deg`): de totalmente transparente para a cor de fundo escura (`#020617`), criando o efeito de escurecimento na parte inferior do card.

***

### Commit 11 — Ajustando o conteúdo do card

**SHA:** `b11e494d`  
**Data:** 07/06/2026 — 20:52

#### O que foi feito

Posicionamento do `<figcaption>` sobre a imagem, na parte inferior do card.

#### Código CSS

```css
.card {
  figcaption {
    position: absolute;
    bottom: 0;
    padding: 24px;

    /* Cards menores têm padding menor */
    &:has(.text-lg) {
      padding: 12px;
    }

    h2 {
      margin-top: 8px;
    }
  }
}
```

#### Conceito: Pseudo-classe `:has()` (CSS relacional)

`:has()` é uma das pseudo-classes mais poderosas do CSS moderno. Ela seleciona um elemento **baseado no que ele contém**. No exemplo:

```css
figcaption:has(.text-lg) {
  padding: 12px;
}
```

Isso aplica `padding: 12px` apenas nas `figcaption` que **contêm** um elemento com classe `.text-lg` (os cards menores). Sem o `:has()`, seria necessário JavaScript ou classes adicionais no HTML para essa lógica condicional.

***

### Commit 12 — Finalizando a seção Destaques

**SHA:** `f945d8fd`  
**Data:** 07/06/2026 — 21:07

#### O que foi feito

Ajustes finais na seção `#featured`: refinamento das proporções do grid, espaçamentos e garantia de que as imagens preenchem corretamente seus containers.

#### CSS do `main` (layout geral da página) em `global.css`

```css
main {
  margin-block: 40px;
  row-gap: 80px;
  column-gap: 32px;

  grid-template-columns: 2fr 1.4fr;

  grid-template-areas:
    "featured featured"
    "weekly   weekly"
    "ai       aside";
}
```

#### Conceito: `grid-template-areas`

A propriedade `grid-template-areas` permite nomear regiões do grid com texto, tornando o layout visual e legível diretamente no CSS.

```
"featured featured"   → ocupa as 2 colunas
"weekly   weekly"     → ocupa as 2 colunas
"ai       aside"      → ai na coluna esquerda, aside na direita
```

Cada seção declara em qual área pertence com `grid-area`:

```css
#featured { grid-area: featured; }
#weekly   { grid-area: weekly; }
#ai       { grid-area: ai; }
aside     { grid-area: aside; }
```

***

### Commit 13 — Estruturando "Mais lidas da semana"

**SHA:** `de29a730`  
**Data:** 07/06/2026 — 21:16

#### O que foi feito

Criação da estrutura HTML da seção `#weekly` com 4 cards de notícias em formato horizontal (imagem + texto).

#### Código HTML — Seção `#weekly`

```html
<section id="weekly">
  <header class="grid grid-flow-col">
    <h3>Mais lidas da semana</h3>
    <a href="#" class="grid grid-flow-col">
      <strong>Ver tudo</strong>
      <span></span>  <!-- ícone de seta via background-image no CSS -->
    </a>
  </header>

  <div class="grid gap-16">
    <figure>
      <span class="content-tag">Veículos</span>
      <img src="./assets/images/Image 06.png" alt="" />
      <p>Protótipo de veículo voador é apresentado...</p>
    </figure>
    <!-- ... 3 figures adicionais -->
  </div>
</section>
```

> **Nota:** O `<span></span>` vazio dentro do link "Ver tudo" recebe uma imagem de fundo SVG via CSS. Esta é uma técnica comum para ícones inline sem precisar de `<img>` ou bibliotecas de ícones.

***

### Commit 14 — Estilizando "Mais lidas da semana"

**SHA:** `a9f54d1d`  
**Data:** 07/06/2026 — 21:28

#### O que foi feito

Aplicação dos estilos na seção `#weekly` e nos cabeçalhos de seção (`.section header`), incluindo o efeito hover na seta do link "Ver tudo".

#### Código CSS — Cabeçalho de seção e link "Ver tudo"

```css
section header {
  border-top: 1px solid var(--stroke-color);
  padding-block: 12px 24px;
  font: var(--text-span);

  a {
    justify-self: end;
    align-items: center;
    gap: 8px;

    /* Ícone via background-image */
    span {
      background-image: url(../assets/icons/ArrowRight.svg);
      width: 16px;
      height: 16px;
    }

    /* Troca o ícone no hover */
    &:hover span {
      background-image: url(../assets/icons/ArrowRight-hover.svg);
    }
  }
}
```

#### Código CSS — Grid dos cards `#weekly`

```css
#weekly {
  grid-area: weekly;

  & > div {
    grid-template-columns: repeat(4, 292px);
  }

  img {
    height: 160px;
  }

  figure {
    position: relative;

    .content-tag {
      position: absolute;
      top: 8px;
      left: 8px;
    }

    p {
      margin-top: 8px;
      font-weight: 800;
    }
  }
}
```

#### Conceito: Troca de ícone via `background-image` no hover

Em vez de usar dois `<img>` e alternar visibilidade com JavaScript, trocamos o SVG de fundo diretamente no CSS:

```css
span {
  background-image: url(../assets/icons/ArrowRight.svg);
}

a:hover span {
  background-image: url(../assets/icons/ArrowRight-hover.svg);
}
```

Isso é uma técnica CSS pura (sem JavaScript) para estados de hover em ícones.

#### Conceito: `& > div` (seletor filho direto no CSS Nesting)

O `>` seleciona apenas filhos **diretos**, não todos os descendentes. Combinado com o `&` do CSS Nesting (que representa o elemento pai `#weekly`):

```css
#weekly {
  & > div {
    /* aplica apenas ao div filho direto de #weekly */
    grid-template-columns: repeat(4, 292px);
  }
}
```

***

### Commit 15 — Estruturando as últimas seções

**SHA:** `1ef63a17`  
**Data:** 07/06/2026 — 21:53

#### O que foi feito

Criação da estrutura HTML das seções `#ai` (Destaques de IA), `aside` (com `#ads` e `#more`), com seus respectivos `<article>`s.

#### Código HTML — Seção `#ai`

```html
<section id="ai">
  <header class="grif grid-flow-col">
    <h3>Destaques da Inteligência Artificial</h3>
    <a href="#" class="grid grid-flow-col">
      <strong>Ver tudo</strong>
      <span></span>
    </a>
  </header>

  <div class="grid gap-32">
    <article class="grid grid-flow-col gap-16">
      <div>
        <span class="content-tag">Inteligência Artificial</span>
        <h3 class="text-xl">Empresa surpreende o mundo ao anunciar...</h3>
        <p class="text-sm">Em um avanço surpreendente da inteligência artificial...</p>
      </div>
      <div>
        <img src="assets/images/Image 10.png" alt="" />
      </div>
    </article>
    <!-- ... 3 articles adicionais -->
  </div>
</section>
```

#### Código HTML — Aside (anúncio + seção "Viu isso aqui?")

```html
<aside>
  <div id="ads">
    <img src="assets/images/Ads.png" alt="" />
  </div>

  <section id="more">
    <header class="grif grid-flow-col">
      <h3>Viu isso aqui?</h3>
      <a href="#" class="grid grid-flow-col">
        <strong>Ver tudo</strong>
        <span></span>
      </a>
    </header>

    <div class="grid gap-32">
      <article class="grid grid-flow-col gap-16">
        <div><img src="assets/images/Image 14.png" alt="" /></div>
        <div>
          <span class="content-tag">Software</span>
          <h3 class="text-xl">Aplicativo de monitoramento ambiental...</h3>
        </div>
      </article>
      <!-- ... 4 articles adicionais -->
    </div>
  </section>
</aside>
```

#### Conceito: `<article>` vs `<section>`

| Elemento | Quando usar |
|---|---|
| `<section>` | Agrupamento temático de conteúdo (grupo de artigos relacionados) |
| `<article>` | Conteúdo autocontido que faz sentido por si só (uma notícia individual) |
| `<aside>` | Conteúdo complementar/relacionado ao conteúdo principal (barra lateral) |

***

### Commit 16 — Estilizando os últimos cards

**SHA:** `b99707c4`  
**Data:** 07/06/2026 — 22:49

#### O que foi feito

Aplicação dos estilos nas seções `#ai`, `aside` e `#more`.

#### Código CSS

```css
#ai {
  grid-area: ai;

  img {
    width: 176px;
    aspect-ratio: 1/1;
    object-fit: cover;
  }

  h3 {
    margin-block: 8px 4px;
  }
}

aside {
  grid-area: aside;
}

#more {
  margin-top: 32px;

  h3 {
    margin: 8px;
  }

  img {
    width: 72px;
    aspect-ratio: 1/1;
    object-fit: cover;
  }
}
```

#### Conceito: `aspect-ratio`

```css
img {
  width: 176px;
  aspect-ratio: 1/1; /* quadrado perfeito */
  object-fit: cover;
}
```

`aspect-ratio` define a proporção largura/altura do elemento. Com `width` definido e `aspect-ratio: 1/1`, a altura é calculada automaticamente para ser igual à largura, garantindo imagens quadradas sem distorção.

#### Conceito: `margin-block` com dois valores

```css
margin-block: 8px 4px;
```

Com dois valores, `margin-block` funciona como: `margin-block-start: 8px` (acima) e `margin-block-end: 4px` (abaixo) — equivalente a `margin-top: 8px; margin-bottom: 4px`.

***

### Commit 17 — Hover nos botões do header

**SHA:** `b8d468f8`  
**Data:** 07/06/2026 — 22:52

#### O que foi feito

Adição do efeito hover nos links do `<nav id="secondary">` e nos elementos clicáveis do header.

#### Código CSS — Hover global em `global.css`

```css
a {
  text-decoration: none;
  color: inherit;
}

a:hover {
  color: var(--brand-color-light);
}
```

#### Conceito: `color: inherit`

Por padrão, links `<a>` têm cor azul e sublinhado definidos pelo navegador. `color: inherit` faz o link herdar a cor do elemento pai, integrando-o ao design sem sobrescritas manuais para cada contexto. O hover aplica a `--brand-color-light` (#60a5fa) como destaque.

***

### Commits 18–25 — Documentação (README)

**SHAs:** `904db515` → `09d7a4c9`  
**Data:** 07/06/2026 — 23:02 às 23:15

#### O que foi feito

Adição, remoção e refinamento do `README.md` do repositório. Houve múltiplos commits de ajuste porque:
1. O README foi criado localmente e adicionado em commits separados.
2. Ocorreu um merge conflict entre a versão local e a versão do GitHub (resolvido com `Merge branch 'main'`).
3. A imagem de demonstração foi adicionada e depois o arquivo foi reestruturado.

#### Conteúdo do README.md final

O README descreve o projeto, lista as tecnologias utilizadas, mostra uma imagem de demonstração e instrui como executar o projeto localmente.

#### Conceito: Merge Commit

O commit `"Merge branch 'main' of https://github.com/..."` é gerado automaticamente pelo Git quando duas histórias divergentes são unidas. Ocorre quando você tem commits locais que ainda não estão no remoto, e o remoto também tem commits novos. O Git cria um commit de merge para unir as duas linhas do tempo.

```bash
# Isso acontece quando você faz:
git pull   # tem commits no remoto que você não tem
git push   # você também tem commits locais não enviados
# → Git cria um merge commit automaticamente
```

> **Dica:** Para evitar merge commits desnecessários em projetos solo, use `git pull --rebase` ao invés de `git pull`.

***

## Conceitos Aplicados no Projeto

### CSS Custom Properties (Variáveis)

Variáveis centralizadas no `:root` criam um **sistema de design** consistente. Qualquer componente do projeto acessa as mesmas cores, fontes e tamanhos através das variáveis.

```css
:root {
  --brand-color-dark: #1d4ed8;
  --bg-color: #0f172a;
  --font-family: "Archivo", sans-serif;
}
```

**Vantagem:** Para mudar o tema do projeto inteiro, basta alterar as variáveis no `:root`.

***

### CSS Grid Layout

O projeto usa Grid em múltiplos níveis:

```css
/* Layout geral da página */
main {
  display: grid;
  grid-template-columns: 2fr 1.4fr;
  grid-template-areas:
    "featured featured"
    "weekly   weekly"
    "ai       aside";
}

/* Grid 2x2 dos cards menores */
.grid-cols-2 {
  grid-template-columns: 1fr 1fr;
}

/* 4 cards lado a lado */
#weekly > div {
  grid-template-columns: repeat(4, 292px);
}
```

***

### CSS Nesting

O CSS Nesting (nativo, sem pré-processador) permite aninhar seletores dentro de outros, melhorando a organização:

```css
/* Sem nesting: */
#primary div { display: flex; }
#primary div:nth-child(2) { margin-inline: auto; }

/* Com nesting: */
#primary {
  div {
    display: flex;
  }
  div:nth-child(2) {
    margin-inline: auto;
  }
}
```

O `&` referencia o seletor pai:
```css
.card {
  &::before { /* equivale a .card::before */ }
  &:has(.text-lg) { /* equivale a .card:has(.text-lg) */ }
}
```

***

### CSS Utility-First

`utility.css` define classes reutilizáveis de propósito único, similar ao conceito do Tailwind CSS:

```css
.grid { display: grid; }
.grid-flow-col { grid-auto-flow: column; }
.grid-cols-2 { grid-template-columns: 1fr 1fr; }
.gap-16 { gap: 16px; }
.gap-32 { gap: 32px; }
.text-2xl { font: var(--h1); }
.text-xl  { font: var(--h2); }
.text-lg  { font: var(--h3); }
.text-sm  { font: var(--text-sm); }
```

**Uso no HTML:**
```html
<div class="grid grid-cols-2 gap-16">
```

***

### HTML Semântico

O projeto usa elementos semânticos corretos para cada conteúdo:

| Elemento | Onde foi usado |
|---|---|
| `<header>` | Cabeçalho da página e de cada seção |
| `<nav>` | Navegação primária e secundária |
| `<main>` | Conteúdo principal da página |
| `<section>` | Agrupamento de notícias por tema |
| `<article>` | Cada notícia individual |
| `<figure>` | Cards com imagem + legenda |
| `<figcaption>` | Legenda das imagens dos cards |
| `<aside>` | Barra lateral com anúncio e "Viu isso aqui?" |

***

### CSS Pseudo-elementos

**`::before` para overlay:**
```css
.card::before {
  content: "";             /* obrigatório para pseudo-elementos */
  position: absolute;
  inset: 0;
  top: 50%;
  background: linear-gradient(180deg, transparent 0%, #020617 100%);
}
```

**Regra:** Todo `::before` e `::after` precisa da propriedade `content` para ser renderizado (mesmo que vazio `""`).

***

## Arquitetura de Arquivos CSS

O projeto separa o CSS em arquivos com responsabilidades distintas, e `index.css` os importa todos:

```css
/* style/index.css */
@import "./global.css";
@import "./utility.css";
@import "./header.css";
@import "./sections.css";
```

| Arquivo | Responsabilidade |
|---|---|
| `global.css` | Reset, variáveis CSS, estilos base (body, a, img, .container, .content-tag) |
| `utility.css` | Classes utilitárias reutilizáveis (grid, gap, text sizes) |
| `header.css` | Estilos exclusivos do `<header>` |
| `sections.css` | Estilos das seções do `<main>` e do `<aside>` |

**Benefício:** Cada arquivo tem uma responsabilidade clara, facilitando manutenção e localização de estilos.

***

*Documentação gerada com base no repositório [https://github.com/martoxm/projeto-portal-de-noticias](https://github.com/martoxm/projeto-portal-de-noticias) — 07/06/2026.*