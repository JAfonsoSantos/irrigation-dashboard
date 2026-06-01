# Smart Irrigation Dashboard

PWA mobile-first para controlar a [smart-irrigation](https://github.com/JAfonsoSantos/smart-irrigation) — sistema de rega automática em Esposende, PT.

**URL:** https://jafonsosantos.github.io/irrigation-dashboard/

## Estrutura

- `index.html` — vista simples (Ontem / Hoje / Amanhã + Manual + Definições)
- `advanced.html` — vista avançada (matriz de 7 dias, edição completa de cron, etc.)
- `config.json` — defaults (hora início + duração por zona). Editado pelo dashboard, lido pelo worker.
- `manifest.json` — manifest PWA (instalável no iPhone)

## Lógica de decisão (v2)

- **SKIP**: choveu >5mm em 48h **OU** prob >70% + >3mm previstos
- **REDUZIDA**: choveu 2-5mm em 48h → metade da duração
- **NORMAL**: duração default (config.json)

**Removido em v2:** modo EXTENDED + ajustes sazonais (Verão/Inverno).

## Zonas (ordem relógio)

1. Norte (ch1, fixo 15min)
2. Oliveira (ch0, configurável)
3. Cozinha (ch1, fixo 15min)
4. Entrada (ch0, configurável)

## Como instalar no iPhone

1. Abrir https://jafonsosantos.github.io/irrigation-dashboard/ no Safari
2. Tocar em "Partilhar" → "Adicionar ao Ecrã Principal"
3. Iniciar com utilizador + palavra-passe + credenciais Shelly/GitHub
