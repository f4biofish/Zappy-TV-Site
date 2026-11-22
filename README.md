# Zappy TV: site de divulgação e download

Site estático do Zappy TV, publicado pelo GitHub Pages a partir da branch `main` (pasta raiz).
Endereço provisório: https://f4biofish.github.io/Zappy-TV-Site/ (o Pages diferencia maiúsculas)

Não tem build nem dependência: é HTML e CSS puros. Para ver no PC, abra o `index.html` no navegador.

## Arquivos

| Arquivo | O que é |
|---|---|
| `index.html` | A página inteira (o CSS está dentro dela, sem JavaScript) |
| `termos.html` | Termos de uso |
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
  Só publicar depois da revisão GPL do avcodec (ver `docs/LICENCAS.md` no repositório do app).

## Cuidados

- Nunca mostrar canais reais, logos de emissoras, capas de filmes reais ou frases como "canais grátis".
- Manter a página leve: hoje são cerca de 120 KB na primeira visita.
- Privacidade e Excluir conta ficam no servidor de licenças; ao trocar para domínio próprio, atualizar os links aqui
  e no `404.html`.
