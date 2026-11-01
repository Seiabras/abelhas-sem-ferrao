# Abelhas sem Ferrão

> **In English:** a site for people who have never heard of Brazil's native stingless bees: they do not sting, where
> they live, what to do when you find a nest and how to start keeping them. It came out of a Design Thinking
> assignment (CEUB, 2026/2): a first version in Lovable, then rebuilt from scratch in HTML, CSS and JavaScript, in
> 13 languages. Live: https://abelhas.linupedia.com.br

Site para quem nunca ouviu falar das abelhas nativas do Brasil: mostra que elas não picam, onde vivem, o que fazer
quando se encontra um ninho e como começar a criar. Nasceu na atividade de Design Thinking da disciplina de
Desenvolvimento de Interfaces (CEUB, 2026/2): a partir da entrevista e do protótipo, gerei uma primeira versão no
Lovable e depois refiz o site do zero em HTML, CSS e JavaScript.

**No ar:** https://abelhas.linupedia.com.br

## Pica ou Não Pica? (1/11/2026)

Em português, o site virou um guia para reconhecer os bichos do Brasil que picam, queimam ou só levam a fama, e
saber o que fazer se picar; as abelhas sem ferrão continuam dentro, como um dos bichos e nas páginas de antes. O nome
é provisório. As outras 12 línguas seguem com o site das Abelhas até a tradução.

| Página | O que tem |
|---|---|
| [`index.html`](index.html) | As quatro portas (Que bicho é?, Picou?, Bichos, Aprender), venenoso × peçonhento, os mais perigosos e os atalhos por lugar |
| [`identificar.html`](identificar.html) | “Que bicho é esse?”: perguntas em árvore até o bicho, com Voltar e Começar de novo |
| [`bichos.html`](bichos.html) | Os 27 bichos, com busca e filtros de grupo, perigo, lugar e região (com mapa no computador) |
| `bicho-<id>.html` | A ficha: pica ou não pica, o perigo, como reconhecer, onde vive, o que fazer, “Não confunda com”, o WhatsApp e a data da revisão |
| [`socorro.html`](socorro.html) | 192, 193 e 0800 722 6001; o que fazer em qualquer picada, o que nunca fazer e cada bicho |
| [`mitos.html`](mitos.html) | 17 mitos e o jogo “Verdade ou mito?” (8 perguntas, recorde guardado no navegador) |
| [`fontes.html`](fontes.html) | As 31 fontes (Ministério da Saúde, Butantan, secretarias de saúde, revistas) |
| [`emergencia.html`](emergencia.html) | “Fui picado”: os três passos, os telefones, o bicho escolhido e o hospital guardado (botão no topo de toda página) |
| [`cartao.html`](cartao.html) | O cartão para mostrar no hospital: bicho, hora (com o tempo passando), sintomas; fica só no aparelho |
| [`soro.html`](soro.html) | Onde tem soro: como funciona e o hospital da cidade, guardado no aparelho |
| [`aprender.html`](aprender.html) | A porta dos jogos, mitos, diferenças, prevenção, números e escola |
| [`jogo.html`](jogo.html) | O jogo “Pica ou não pica?”: 10 bichos, 6 segundos cada (dá para tirar o limite) |
| [`diferencas.html`](diferencas.html) | Os bichos parecidos lado a lado, com o detalhe desenhado, e o jogo “Qual dos dois?” |
| [`prevenir.html`](prevenir.html) | O teste “Minha casa está segura?”, crianças, cães e gatos e a época de cada bicho |
| [`numeros.html`](numeros.html) | Os acidentes de 2023 no Brasil, por bicho (Ministério da Saúde) |
| [`escola.html`](escola.html) | Plano de aula, duas atividades, cartaz e respostas, para imprimir (uma folha por página) |

O script é o `js/guia.js`. Nas três versões: no celular, o menu de 5 itens fica embaixo, os mais perigosos numa faixa
e o botão “Ligar 192” preso acima do menu; no tablet, cartões em 2 colunas e os telefones numa linha; no computador,
filtros, telefones e o aviso “Alguém foi picado?” parados numa coluna ao lado, e cartões em 3 ou 4 colunas. Conferido
com o axe 4.10 em 390, 820 e 1280 px, nos modos claro e escuro: nenhuma falha.

**Sem internet:** o `sw.js` guarda o Socorro, o “Fui picado”, o cartão e as páginas principais na primeira visita, e a
caixa “Guardar o guia” guarda o resto. O que a pessoa marca (o hospital, o cartão, o teste da casa, os recordes) fica só
no `localStorage` do navegador.

**Não substitui o atendimento médico:** em caso de acidente, ligue 192 ou vá ao serviço de saúde mais perto.

## Páginas

| Página | O que tem |
|---|---|
| [`index.html`](index.html) | A pergunta de abertura, a jataí, a uruçu e a mandaçaia, e os cartões “Comece por aqui” |
| [`descobrir.html`](descobrir.html) | Percurso de 3 telas com barra de progresso |
| [`achei-um-ninho.html`](achei-um-ninho.html) | O passo a passo do que fazer e de como pedir o resgate |
| [`criar.html`](criar.html) | “Posso criar?”: como começar a criar abelhas nativas em casa, o mel e o que não fazer (31/10/2026) |
| [`teste.html`](teste.html) | Teste de 5 perguntas, com a resposta certa ou errada na hora |
| [`creditos.html`](creditos.html) | Autor e licença de cada foto |

### Scripts

| Arquivo | O que faz |
|---|---|
| `js/tema-inicio.js` | No `<head>`, sem `defer`: aplica o tema escolhido antes de desenhar a página |
| `js/tema.js` | O botão de tema: troca e guarda a escolha; sem escolha, segue o sistema |
| `js/percurso.js` | O percurso “Descobrir em 3 minutos”: uma tela por vez e a barra de progresso |
| `js/teste.js` | O teste: cinco perguntas, uma por vez, a resposta na hora e a nota no fim |

## Acessibilidade

- Contraste: o texto principal tem 13,56:1 sobre o creme, e o texto secundário, 6,91:1. O mel (`#E9A23B`) só leva
  texto escuro e o verde-folha (`#3F6B3A`), texto branco.
- O percurso e o teste avisam as mudanças para leitores de tela e levam o foco ao título de cada tela.
- No teste, a resposta não depende só da cor: cada retorno também diz “Certo!” ou “Não é essa.”, com a explicação.
- Toda página tem um `h1`, e os links do rodapé têm pelo menos 24 px de altura (WCAG 2.2, 2.5.8).
- Conferido com o axe 4.10 em 31/10/2026, no modo claro e no escuro: nenhuma falha em nenhuma página.

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

## Três versões: celular, tablet e computador (1/11/2026)

Pela regra 6 do linuarquivos, cada aparelho tem o seu layout, só com CSS (o mesmo HTML nas 13 línguas):

| | Celular (até 699 px) | Tablet (700 a 1099 px) | Computador (1100 px ou mais) |
|---|---|---|---|
| Navegação | menu numa barra presa embaixo; no topo, só o nome e o tema | menu no topo | menu no topo |
| “Comece por aqui” | ladrilhos em 2 colunas | 2 × 2 | os 4 numa linha |
| Abertura | texto e fotos em uma coluna | texto ao lado das fotos | texto ao lado das fotos, maior |

