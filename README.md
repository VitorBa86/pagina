# Método LuanaCorre — Wellness club de corrida

Landing page do Método LuanaCorre: treinos de corrida guiados em grupo, planilha para o ritmo de cada aluno e cuidado com o corpo fora da pista. O objetivo da página é levar o visitante a agendar um treino experimental pelo WhatsApp.

Página estática (HTML + CSS em um único arquivo), sem build e sem dependências.

## Estrutura

```
.
├── index.html          # página final, a que vai ao ar
├── imagens/            # imagens otimizadas (.webp) e logos
│   └── imagens.json    # briefing de cada slot de imagem (seção, tamanho, origem)
├── fonte/
│   ├── modelo.html     # modelo com marcadores {{ic:...}} e {{wa:...}}
│   └── .icones/        # cache dos ícones SVG usados pelo modelo
└── .nojekyll           # faz o GitHub Pages servir os arquivos como estão
```

## Ver localmente

Abra o `index.html` no navegador, ou sirva a pasta:

```bash
python3 -m http.server 8000
# http://localhost:8000
```

## Gerar o index.html a partir do modelo

O `index.html` é gerado a partir de `fonte/modelo.html` pelo script `montar_pagina.py` da skill PageBrain, que troca os marcadores por ícones SVG e links de WhatsApp. Para mudar o número do WhatsApp, rode de novo:

```bash
python3 caminho/para/pagebrain/scripts/montar_pagina.py fonte/modelo.html index.html --numero 55DDXXXXXXXXX
```

Edite sempre o `fonte/modelo.html` e gere o `index.html` de novo, para as duas versões não divergirem.

## Antes de publicar

- [ ] Trocar o número de WhatsApp de exemplo (`5519999999999`) pelo real
- [ ] Trocar o ID do Google Ads `AW-XXXXXXXXXX` (ou remover o bloco do `<head>`)
- [ ] Conferir o CREF e o e-mail de contato

## Publicar no GitHub Pages

1. Suba o repositório para o GitHub.
2. Em **Settings → Pages**, escolha **Deploy from a branch**, branch `main`, pasta `/ (root)`.
3. A página fica em `https://<usuario>.github.io/<repositorio>/`.
