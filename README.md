# Estúdio Gabriela

Site institucional da marca de bordados manuais. Site estático (HTML + CSS + SVG),
sem build e sem dependências.

Publicado em <https://estudiogabriela.com.br> via GitHub Pages.

## Estrutura

```
index.html                    página única (todo o CSS e JS estão inline)
favicon.ico                   ícone 16/32/48px — fica na raiz de propósito
assets/
  favicon.svg                 ícone vetorial (a flor da marca, recortada)
  apple-touch-icon.png        ícone 180px para "adicionar à tela de início" no iOS
  flor.svg                    flor da marca com as folhas (seção "cursos")
  agulha.svg                  agulha da animação de bordado
  logo-principal.svg          logo colorido (cabeçalho e hero)
  logo-principal_negativa.svg logo para fundo escuro (rodapé)
  images/
    trabalho-01..06.jpg       galeria da seção "trabalhos"
    gabriela.jpg              foto da seção "sobre"
CNAME                         domínio próprio do GitHub Pages — não apagar
.nojekyll                     desliga o processamento Jekyll do GitHub Pages
```

## Como trocar as fotos

1. Substitua o arquivo em `assets/images/` mantendo **o mesmo nome**
   (ex.: uma foto nova vira `trabalho-03.jpg`). Assim não é preciso mexer no HTML.
2. Prefira imagens **quadradas** (a galeria recorta em 1:1) e com no máximo
   ~1600px de lado — arquivos muito grandes deixam o site lento.
3. Publique:

```bash
git add assets/images
git commit -m "Atualiza fotos da galeria"
git push
```

O site atualiza sozinho em ~1 minuto.

Para **adicionar** uma foto (em vez de trocar), copie o arquivo para
`assets/images/` e acrescente uma linha dentro de `<div class="gal">` no `index.html`:

```html
<figure><img src="assets/images/trabalho-07.jpg" alt="Bordado à mão — Estúdio Gabriela" loading="lazy"></figure>
```

## Rodar localmente

O `index.html` carrega os SVGs via `fetch`, então abrir o arquivo direto pelo
navegador (`file://`) não mostra a animação do logo. Suba um servidor local:

```bash
python -m http.server 8000
# abra http://localhost:8000
```
