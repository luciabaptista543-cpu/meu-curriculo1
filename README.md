> ⚠️ **Nota:** este ficheiro foi gerado a partir de um template partilhado. Onde vir texto entre colchetes [assim], ou comentários "Lúcia: ...", substitua pela sua informação real antes de entregar.

# Site de Currículo Pessoal — Lúcia Baptista

**Estudante:** Lúcia Baptista
**Turma:** 2º Ano — Licenciatura em Informática — Programação de Design Web
**Instituição:** Universidade Licungo, Moçambique

## Descrição do projeto

Site pessoal de currículo/portfólio composto por 5 páginas HTML interligadas,
construído **apenas com HTML5 e CSS3 puros** — sem frameworks CSS (Bootstrap,
Tailwind, etc.) e sem JavaScript. Toda a interatividade (menu responsivo,
destaque do link ativo, campos de formulário personalizados) foi conseguida
unicamente com seletores e pseudo-classes CSS (`:checked`, `:hover`,
`:focus`, `:nth-child`, etc.).

### Como visualizar

1. Descarregue ou clone este repositório.
2. Abra o ficheiro `index.html` diretamente no navegador (não é necessário
   servidor nem instalação de dependências).
3. Navegue pelo site através do menu no topo de cada página.

> **Nota sobre os ficheiros multimédia:** as pastas `assets/img/`,
> `assets/video/`, `assets/audio/` e `assets/ficheiros/` contêm ficheiros de
> exemplo com nomes já referenciados no HTML (ex.: `avatar.jpg`,
> `apresentacao.mp4`, `apresentacao.mp3`, `cv.pdf`). Substitua-os pelos seus
> próprios ficheiros, mantendo os mesmos nomes, ou atualize os caminhos no
> HTML se preferir outros nomes.

## Páginas do site

| Página | Ficheiro | Conteúdo |
|---|---|---|
| Home | `index.html` | Apresentação pessoal, foto/avatar, tagline, vídeo de apresentação (`<video>`), áudio de apresentação (`<audio>`) e chamada para ação para a página de contacto. |
| Sobre / Currículo | `about.html` | Formação académica (`<ol>`), experiência (`<ul>`), certificados (`<figure>`/`<figcaption>`) e tabela de competências técnicas com `colspan`/`rowspan`. |
| Portfólio / Projetos | `portfolio.html` | Grelha de projetos em cartões, construída com **CSS Grid**, incluindo um vídeo de demonstração incorporado via `<iframe>` do YouTube. |
| Hobbies / Interesses | `hobbies.html` | Cartões de hobbies organizados com **Flexbox**, explorando `flex-direction`, `flex-wrap`, `justify-content` e `align-items`. |
| Contacto | `contact.html` | Formulário completo com todos os tipos de campo pedidos e validação nativa HTML5. |

## Estrutura de pastas

```
meu-curriculo/
├── index.html
├── about.html
├── portfolio.html
├── hobbies.html
├── contact.html
├── css/
│   ├── estilo.css        → estilos partilhados: header, footer, tipografia, variáveis
│   └── responsivo.css    → media queries (mobile-first)
├── assets/
│   ├── img/               → fotos, ícones, capturas de ecrã
│   ├── video/              → vídeo local usado na tag <video>
│   ├── audio/               → áudio local usado na tag <audio>
│   └── ficheiros/            → CV em PDF
└── README.md
```

## Principais tags e recursos utilizados, e o seu papel

### HTML5 semântico
- **`<header>`** — cabeçalho fixo (sticky) com o nome do estudante e o menu de navegação, repetido de forma idêntica em todas as páginas.
- **`<nav>`** — agrupa a lista de ligações do menu principal, com `aria-label` para leitores de ecrã.
- **`<main>`** — delimita o conteúdo principal e único de cada página (landmark de acessibilidade).
- **`<section>`** — divide o conteúdo em blocos temáticos (hero, vídeo, formação, competências, etc.).
- **`<article>`** — usado nos cartões de projetos e hobbies, por representarem conteúdo autónomo e reutilizável.
- **`<aside>`** — reservado para conteúdo complementar (pode ser usado, por exemplo, para uma nota lateral no currículo).
- **`<footer>`** — rodapé com contactos, redes sociais e assinatura, igual em todas as páginas.
- **`<figure>` / `<figcaption>`** — usados sempre que uma imagem tem legenda (certificados, capturas de ecrã de projetos).
- **`<fieldset>` / `<legend>`** — agrupam campos relacionados no formulário de contacto (ex.: "Dados pessoais").

### Elementos multimédia
- **`<img alt="...">`** — todas as imagens têm texto alternativo descritivo (nunca vazio ou genérico).
- **`<video controls poster="..."><source ... type="video/mp4"></video>`** — vídeo de apresentação nativo na Home, com pré-visualização (`poster`) e múltiplas fontes.
- **`<iframe>` (YouTube)** — vídeo de demonstração de projeto incorporado no Portfólio, como segunda forma de vídeo.
- **`<audio controls><source ... type="audio/mpeg"></audio>`** — apresentação em áudio na Home.

### CSS — seletores e pseudo-classes/elementos
- **Seletores de descendência, filho direto (`>`), irmão adjacente (`+`) e de atributo** (`input[type="email"]`) — usados em `css/estilo.css` para estilizar campos do formulário e linhas da tabela sem adicionar classes extra.
- **`:hover`, `:focus`/`:focus-visible`** — feedback visual em botões, links e campos de formulário.
- **`:nth-child(even)`** — efeito "zebra" nas linhas da tabela de competências.
- **`::before` / `::after`** — usados no menu (marcador do item ativo), no cartão (barra decorativa animada) e na barra de nível de competência.
- **`:checked`** — base do menu "hamburger" só-CSS (checkbox escondido) e da personalização dos campos `radio`/`checkbox`.

### Layout
- **Flexbox** (`hobbies.html`) — `flex-direction`, `flex-wrap`, `justify-content` e `align-items` são explorados em duas secções com configurações diferentes.
- **CSS Grid** (`portfolio.html`) — `grid-template-columns: repeat(auto-fit, minmax(...))` cria uma grelha de cartões totalmente responsiva sem media queries adicionais.
- **`position: sticky`** — aplicado ao `<header>`, para que o menu se mantenha visível durante o scroll. A diferença entre `static`, `relative`, `absolute`, `fixed` e `sticky` está explicada em comentário no topo de `css/estilo.css`.

### Responsividade
- **`<meta name="viewport" content="width=device-width, initial-scale=1.0">`** em todas as páginas.
- **Abordagem mobile-first**: `css/estilo.css` contém os estilos-base pensados para ecrã pequeno; `css/responsivo.css` usa `@media (min-width: ...)` para ampliar o layout a partir de 481px e 769px.
- **Unidades relativas** (`rem`, `%`, `vw`, `clamp()`) combinadas com unidades fixas (`px` em bordas e sombras, onde a precisão visual importa).

### Estilo visual avançado
- **Variáveis CSS (`:root`)** — cores, tipografia e espaçamentos centralizados em `css/estilo.css`, facilitando qualquer alteração futura da identidade visual.
- **`transition`** — usada em botões, cartões e campos de formulário.
- **`@keyframes surgir`** — pequena animação de entrada no *hero* da Home, respeitando `prefers-reduced-motion`.
- **`linear-gradient` e `box-shadow`/`text-shadow`** — usados na barra de nível de competências, no botão de destaque e nos cartões.
- **Tipografia**: `Space Grotesk` (títulos), `Inter` (corpo de texto) e `JetBrains Mono` (rótulos estilo "código"), formando uma identidade visual coerente inspirada num editor de código.

### Formulário e validação (apenas HTML5, sem JavaScript)
- `required`, `minlength`, `maxlength` — campo Nome e Mensagem.
- `type="email"` — validação nativa de formato de email pelo navegador.
- `pattern="8[2-7][0-9]{7}"` — validação do formato de telefone moçambicano.
- `type="date"` — seleção de data preferida de contacto.
- `type="number" min="0" max="23"` — hora preferida de contacto.
- `type="file" accept=".pdf,.doc,.docx"` — anexo do CV, restringindo os tipos de ficheiro aceites.
- `<select>` obrigatório, grupo de `radio` e grupo de `checkbox`, todos com `<label>` associado por `for`/`id` e estilizados via CSS (`appearance: none` + pseudo-elementos), substituindo a aparência padrão do navegador.

### Acessibilidade
- Ligação "Saltar para o conteúdo" no início de cada página.
- Todos os campos do formulário têm `<label>` associado.
- Contraste de cor pensado para leitura confortável sobre fundo escuro.
- `aria-label`, `aria-current="page"` e `aria-hidden="true"` (em ícones puramente decorativos) usados de forma criteriosa.
- Foco de teclado sempre visível (`:focus-visible`).

## Histórico de commits

Recomenda-se registar a evolução do trabalho em commits distintos, por
exemplo: estrutura HTML das páginas → estilos base e variáveis → header/nav
e footer partilhados → Grid do Portfólio → Flexbox dos Hobbies → formulário
de Contacto e validação → responsividade → ajustes finais de acessibilidade.

## Capturas de ecrã

*(Adicionar aqui, opcionalmente, capturas de ecrã de cada página depois de
adicionar as suas próprias imagens/vídeos/áudio.)*
