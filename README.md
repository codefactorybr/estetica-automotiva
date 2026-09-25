# Verniz Estúdio Automotivo — modelo de demonstração

Landing page premium para estética automotiva. **Todos os dados são fictícios** (nome, endereço, telefone, depoimentos).

## Estrutura

```
index.html          # página completa e autocontida (runtime, React, fontes e imagens principais embutidos)
vercel.json         # configuração mínima (URLs limpas)
assets/
├── favicon.svg
├── og-image.jpg    # imagem de compartilhamento 1200×630
└── img/            # fotos carregadas sob demanda (serviços, antes/depois, processo, galeria ampliada)
README.md
```

Site estático: sem build, sem framework, sem package.json. Os `{{ ... }}` que aparecem no código-fonte são preenchidos pelo JavaScript embutido no próprio `index.html` quando a página abre no navegador. Ver o código-fonte (Ctrl+U) sempre mostra os `{{ }}`; isso é esperado.

**Importante:** a pasta `assets/img/` precisa ir para o GitHub junto com o `index.html`, com os nomes exatamente como estão (tudo minúsculo).

## Rodar localmente

```
npx serve .
# ou
python3 -m http.server 8080
```

## Publicar na Vercel

1. Crie um repositório no GitHub com o conteúdo desta pasta na raiz.
2. Na Vercel: **Add New → Project →** importe o repositório.
3. Framework Preset: **Other**. Build Command: vazio. Output Directory: `.` (raiz).
4. Deploy.

Se preferir manter a pasta `site/` dentro de um repositório maior, defina **Root Directory = site** nas configurações do projeto.

A tag `og:image` já aponta para `https://estetica-automotiva-v.vercel.app/assets/og-image.jpg`. Troque ao mudar de domínio.

## Duplicar para um cliente

O `index.html` é gerado a partir do arquivo-fonte editável do projeto (`Verniz Demo.dc.html`). Edite o fonte (textos, telefone, endereço, dados em `chData`, `baData`, `procSteps`, `revData`, `faqData`, `galSrc`) e gere o `index.html` de novo.

Valores da demo a substituir: `VERNIZ` / `Verniz Estúdio Automotivo`, `5511900002026`, `(11) 90000-2026`, `Rua dos Artífices, 214 — Vila Madalena`, `05433-000`, `@verniz.studio`, `contato@verniz.studio`, horários e o termo do mapa `Vila%20Madalena%2C%20S%C3%A3o%20Paulo`.

## Dependências externas

- Google Fonts (Archivo, IBM Plex Mono)
- Google Maps (iframe do mapa)
