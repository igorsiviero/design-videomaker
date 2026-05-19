# Horizon Portfólios — versão estática unificada

Esta versão contém **uma única URL** para os portfólios de Design e Vídeo.

## Arquivo principal

Abra ou publique:

```txt
index.html
```

No menu do header, use:

```txt
Portfólio Design
Portfólio Vídeo
```

Ambos ficam na mesma URL, alternando por `#design` e `#video`.

## Estrutura esperada

```txt
assets/
├─ data/
│  └─ portfolio.json
├─ js/
│  └─ portfolio-data.js
├─ uploads/
│  ├─ design/
│  └─ video/
└─ img/
   ├─ horizon-logo.png
   └─ horizon-logo-footer.png
```

## Por que a versão anterior pode não ter funcionado

A versão anterior dependia de `fetch()` para ler `assets/data/portfolio.json`.

Quando você abre o HTML por duplo clique no Windows, usando `file://`, alguns navegadores bloqueiam a leitura de JSON local. Nesta versão, os dados também ficam em:

```txt
assets/js/portfolio-data.js
```

Isso permite abrir o arquivo localmente e também publicar no GitHub Pages.

## Como atualizar os projetos depois

1. Copie os arquivos de mídia para:

```txt
assets/uploads/design/
assets/uploads/video/
```

2. Copie o JSON novo para:

```txt
assets/data/portfolio.json
```

3. Rode:

```bat
GERAR-DADOS-ESTATICOS.bat
```

Esse BAT atualiza o arquivo:

```txt
assets/js/portfolio-data.js
```

## Copiar do projeto completo com upload

Rode:

```bat
COPIAR-DO-PROJETO-ORIGINAL.bat "C:\caminho\horizon-portfolio-app"
```

Ele copia:

```txt
data/portfolio.json
public/assets/uploads/
```

e gera automaticamente o `portfolio-data.js`.

## GitHub Pages

Suba o conteúdo desta pasta para o GitHub. O GitHub Pages deve apontar para a raiz onde está o `index.html`.

## Observação sobre fontes

A estrutura já referencia `HelveticaNowDisplay`, mas os arquivos `.ttf` não estão incluídos por licenciamento. Coloque manualmente os arquivos em:

```txt
assets/fonts/
```

## Ajuste visual dos vídeos

Nesta versão, os vídeos horizontais não ocupam mais uma largura maior que os verticais. A aba de vídeos usa uma grade harmonizada: todos os cards possuem a mesma largura base, mantendo a proporção do vídeo dentro da miniatura.
