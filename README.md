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
| `sitemap.xml` | Lista de páginas para o Google (atualizar ao criar página nova) |
| `assets/compartilhar.jpg` | Imagem que aparece ao compartilhar o link (1200x630) |
| `robots.txt`, `.nojekyll` | Para buscadores, e para o Pages servir os arquivos como estão |
| `LICENCAS.md` | Licença da fonte |
| `teste/`, `en/test/`, `es/prueba/` | Página temporária dos testadores (veja abaixo) |
| `en/`, `es/` | As mesmas páginas em inglês e espanhol (`index.html`, `termos.html`, `licencas.html`) |

## Idiomas

O site existe em português (raiz), inglês (`/en/`) e espanhol (`/es/`). Não há redirecionamento automático:
quem chega escolhe no seletor "PT · EN · ES" do topo, e o Google mostra cada versão pelo idioma da busca
(marcações `hreflang` em cada página e no `sitemap.xml`; o `x-default` é o português).

- **Toda mudança de texto, botão, versão ou SHA-256 vale para as três pastas.** Mexa nos três arquivos.
- Termos em inglês e espanhol dizem que, se houver diferença, vale a versão em português. Ao mudar os termos,
  atualize as três versões e a data.
- Links para Privacidade e Excluir conta levam `?lang=en` ou `?lang=es`, para o servidor abrir no mesmo idioma.
- Página nova: crie nas três pastas, com `canonical`, os quatro `<link rel="alternate" hreflang>` e o seletor,
  e acrescente ao `sitemap.xml`.
- As imagens das telas são as mesmas nos três idiomas (o app aparece em português).

## Quando um app for publicado

Os botões das lojas estão como "Em breve" (um `<span class="... breve">`). Em `index.html`, `en/index.html` e
`es/index.html`, em dois lugares de cada (topo da página e seção `#download`):

1. Troque o `<span ... aria-disabled="true">` por `<a href="LINK" target="_blank" rel="noopener">`
   (e o `</span>` de fechamento por `</a>`).
2. Tire a palavra `breve` da classe e a etiqueta (`Em breve`, `Coming soon`, `Muy pronto`).
3. Quando todos estiverem publicados, apague a frase "Google Play e Amazon em breve." do topo (e a de cada idioma).

Links:
- Google Play (TV e celular): `https://play.google.com/store/apps/details?id=br.com.zappy.tv`
- Amazon Appstore (Fire TV): o link da ficha, quando existir. **Sem preço nem "assine" perto dele** (regra da Amazon).
- Windows: `https://github.com/f4biofish/Zappy-TV-Site/releases/latest/download/ZappyTV-windows.msi`
  (o MSI vai como arquivo de um Release deste repositório, sempre com esse nome, tag `windows-vX.Y.Z`).
  Revisão feita em 21/11/2026: o avcodec do VLC 3.0.21 é "LGPL version 2.1 or later". Ao trocar a versão do VLC,
  repetir a checagem (ver `docs/LICENCAS.md` no repositório do app) e atualizar `licencas.html`.
  A cada versão nova: atualizar versão, tamanho e SHA-256 no cartão do Windows nos três `index.html`.

## Cuidados

- Nunca mostrar canais reais, logos de emissoras, capas de filmes reais ou frases como "canais grátis".
- Manter a página leve: hoje são cerca de 120 KB na primeira visita.
- Privacidade e Excluir conta ficam no servidor de licenças; se o servidor ganhar um subdomínio (ex.: api.zappytv.app.br),
  atualizar esses links nas páginas das três pastas.

## Página dos testadores (temporária)

Durante o teste fechado da Google Play existe uma página só para quem recebe o convite:
`/teste/` (português), `/en/test/` (inglês) e `/es/prueba/` (espanhol). Ela fica **fora do Google**
(`noindex`), fora do `sitemap.xml` e fora do menu. Os links (grupo, ativar teste, Play e formulário) estão
nos três `index.html`; se algum mudar, troque nos três.

**Depois do lançamento:** substitua o conteúdo dos três arquivos por um redirecionamento para a página
inicial do mesmo idioma (por exemplo `<meta http-equiv="refresh" content="0; url=/">` com `noindex`),
para quem tiver o link antigo não cair numa página desatualizada.
