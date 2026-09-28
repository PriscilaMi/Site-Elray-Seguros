# ELRAY SEGUROS — Site Institucional

Site estático (HTML + Tailwind via CDN), sem necessidade de build ou servidor.

## Estrutura

```
elray-site/
├── index.html
├── render.yaml
└── assets/
    ├── img/
    │   └── logo.jpg
    └── video/
        └── institucional.mp4   ← ADICIONE ESTE ARQUIVO (veja abaixo)
```

## ⚠️ Vídeo institucional pendente

O link do Google Drive que você enviou não pôde ser baixado automaticamente
(o Drive exige login para baixar o arquivo bruto, e não é acessível por
ferramentas externas). O site já está pronto para exibir o vídeo — falta
apenas colocar o arquivo no lugar certo:

1. Baixe o vídeo do Google Drive para o seu computador.
2. Renomeie o arquivo para `institucional.mp4`.
3. Coloque-o dentro da pasta `assets/video/`, substituindo o placeholder.
4. Suba (commit + push) essa alteração no GitHub.

Se o arquivo for muito grande (mais de ~50–80 MB), o ideal é comprimir o
vídeo antes (ex.: HandBrake, ou `ffmpeg -i original.mp4 -vcodec libx264
-crf 28 institucional.mp4`) para o site carregar rápido.

## Publicar no GitHub

```bash
cd elray-site
git init
git add .
git commit -m "Site institucional ELRAY SEGUROS"
git branch -M main
git remote add origin https://github.com/SEU-USUARIO/elray-seguros.git
git push -u origin main
```

### Opção A — GitHub Pages (grátis, mais simples)
1. No repositório, vá em **Settings → Pages**.
2. Em "Branch", selecione `main` e a pasta `/ (root)`.
3. Salve. Em alguns minutos o site estará em
   `https://SEU-USUARIO.github.io/elray-seguros/`.

### Opção B — Render (Static Site)
1. Entre em [render.com](https://render.com) e clique em **New → Static Site**.
2. Conecte sua conta do GitHub e selecione o repositório `elray-seguros`.
3. Configure:
   - **Build Command:** (deixe em branco — não há build)
   - **Publish Directory:** `.`
4. Clique em **Create Static Site**. O arquivo `render.yaml` incluso já
   preenche essas configurações automaticamente se você usar "Deploy from
   render.yaml" (Blueprint).

## Domínio próprio

Depois de publicado (GitHub Pages ou Render), você pode apontar o domínio
`elrayseguros.com.br` (ou o que preferir) nas configurações de domínio
customizado de cada plataforma.

## Editar textos, telefone ou endereço

Todo o conteúdo está em `index.html`, em português, organizado por seções
comentadas (`<!-- HERO -->`, `<!-- SERVIÇOS -->`, `<!-- BLOG -->` etc.).
Basta abrir o arquivo em qualquer editor de texto e alterar diretamente.
