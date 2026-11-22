# Zappy TV: site de divulgação e download

Site estático do Zappy TV, publicado pelo GitHub Pages a partir da branch `main` (pasta raiz).
Endereço: **https://zappytv.app.br** (domínio no registro.br, arquivo `CNAME`). O endereço antigo
https://f4biofish.github.io/Zappy-TV-Site/ redireciona para ele.

DNS no registro.br: 4 registros A em `zappytv.app.br` (185.199.108.153, .109.153, .110.153, .111.153)
e CNAME `www` → `f4biofish.github.io`. Em Settings → Pages: domínio `zappytv.app.br` e "Enforce HTTPS".

Não tem build nem dependência: é HTML e CSS puros. Para ver no PC, abra o `index.html` no navegador.

## Arquivos

| Arquivo | O que é |
|---|---|
| `index.html` | A página inteira (o CSS está dentro dela, sem JavaScript) |
| `termos.html` | Termos de uso |
| `licencas.html` | Licenças de software livre (libVLC/FFmpeg LGPL no Windows, fonte Inter) |
| `404.html` | Página de endereço não encontrado |
| `assets/inter.woff2` | Fonte Inter (só letras latinas, todos os pesos num arquivo de 48 KB) |
| `assets/tela-tv.webp`, `assets/tela-celular.webp` | Telas do app com conteúdo fictício |
| `favicon.svg`, `apple-touch-icon.png` | Ícone da aba e do atalho no celular |
| `robots.txt`, `.nojekyll` | Para buscadores, e para o Pages servir os arquivos como estão |
| `LICENCAS.md` | Licença da fonte |

## Quando um app for publicado

Os botões das lojas estão como "Em breve" (um `<span class="... breve">`). Em `index.html`, em dois lugares
(topo da página e seção `#download`):

1. Troque o `<span ... aria-disabled="true">` por `<a href="LINK" target="_blank" rel="noopener">`
   (e o `</span>` de fechamento por `</a>`).
2. Tire a palavra `breve` da classe e a `<span class="etiqueta">Em breve</span>`.
3. Quando todos estiverem publicados, apague a frase "Em breve nas lojas." do topo.

Links:
- Google Play (TV e celular): `https://play.google.com/store/apps/details?id=br.com.zappy.tv`
- Amazon Appstore (Fire TV): o link da ficha, quando existir. **Sem preço nem "assine" perto dele** (regra da Amazon).
- Windows: `https://github.com/f4biofish/Zappy-TV-Site/releases/latest/download/ZappyTV-windows.msi`
  (o MSI vai como arquivo de um Release deste repositório, sempre com esse nome, tag `windows-vX.Y.Z`).
  Revisão feita em 21/11/2026: o avcodec do VLC 3.0.21 é "LGPL version 2.1 or later". Ao trocar a versão do VLC,
  repetir a checagem (ver `docs/LICENCAS.md` no repositório do app) e atualizar `licencas.html`.
  A cada versão nova: atualizar versão, tamanho e SHA-256 no cartão do Windows em `index.html`.

## Cuidados

- Nunca mostrar canais reais, logos de emissoras, capas de filmes reais ou frases como "canais grátis".
- Manter a página leve: hoje são cerca de 120 KB na primeira visita.
- Privacidade e Excluir conta ficam no servidor de licenças; se o servidor ganhar um subdomínio (ex.: api.zappytv.app.br),
  atualizar esses links em `index.html`, `termos.html` e `licencas.html`.
