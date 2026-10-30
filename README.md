# Abelhas sem Ferrão

Site para quem nunca ouviu falar das abelhas nativas do Brasil: mostra que elas não picam, onde vivem e o que fazer
quando se encontra um ninho. Nasceu na atividade de Design Thinking da disciplina de Desenvolvimento de Interfaces
(CEUB, 2026/2): a partir da entrevista e do protótipo, gerei uma primeira versão no Lovable e depois refiz o site do
zero em HTML, CSS e JavaScript.

**No ar:** https://abelhas.linupedia.com.br

## Páginas

| Página | O que tem |
|---|---|
| [`index.html`](index.html) | A pergunta de abertura, a jataí, a uruçu e a mandaçaia, e os cartões “Comece por aqui” |
| [`descobrir.html`](descobrir.html) | Percurso de 3 telas com barra de progresso |
| [`achei-um-ninho.html`](achei-um-ninho.html) | O passo a passo do que fazer e de como pedir o resgate |
| [`teste.html`](teste.html) | Teste de 5 perguntas, com a resposta certa ou errada na hora |
| [`creditos.html`](creditos.html) | Autor e licença de cada foto |

## Acessibilidade

- Contraste: o texto principal tem 13,56:1 sobre o creme, e o texto secundário, 6,91:1. O mel (`#E9A23B`) só leva
  texto escuro e o verde-folha (`#3F6B3A`), texto branco.
- O percurso e o teste avisam as mudanças para leitores de tela e levam o foco ao título de cada tela.
- No teste, a resposta não depende só da cor: cada retorno também diz “Certo!” ou “Não é essa.”, com a explicação.

## Idiomas

O site está em 13 idiomas: português do Brasil na raiz e `/pt-pt/`, `/es/`, `/ca/`, `/nl/`, `/en/`, `/fr/`, `/de/`,
`/it/`, `/intl/` (inglês internacional), `/ja/`, `/ko/` e `/zh-hant/`, com os outros idiomas no rodapé (o percurso e o teste respondem no idioma da página) e as
alternativas de cada página para os buscadores. As páginas de cada idioma são geradas no repositório do
[Linu Sites](https://github.com/Seiabras/linu-sites) (o modelo e os textos ficam em `ferramentas/estudo/abelhas-sem-ferrao/`); aqui ficam as
páginas prontas. As frases que o script escreve vão num `<script type="application/json">` em cada página.

## Modo claro e escuro

Segue o tema do sistema e tem um botão no topo para trocar, que guarda a escolha. O `js/tema-inicio.js` aplica o tema
antes de pintar (sem piscar a página clara) e o `js/tema.js` cuida do botão. As cores do modo escuro também foram
medidas pela fórmula de contraste da WCAG, com a mesma regra do modo claro.

## Fotos

Todas são do [Wikimedia Commons](https://commons.wikimedia.org/), com licença livre, e foram apenas redimensionadas.
O autor e a licença de cada uma estão na página de créditos e em `img/creditos.json`.

## Como abrir

É só abrir o `index.html` no navegador; não tem build nem dependência.

## Segurança

Segue a política de segurança dos sites do Linu Sites: tudo vem do próprio endereço, sem CDN e sem estilo ou script
dentro do HTML (por isso não há nenhum `style="…"`: tudo está em classes no `css/estilo.css`).
