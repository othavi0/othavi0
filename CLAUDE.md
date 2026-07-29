# othavi0 — profile README

Decisões de marca deste repo (fonte movida da memória global em 2026-07-29).

## Identidade e estilo (híbrido deliberado)

- Paleta **One Dark Pro** no README: `#21252b` bg, `#d7dae0` ink, `#abb2bf` body, `#5c6370` muted, `#e06c75` coral = **acento único**. Tipografia/voz do site othavio.com (Geist Mono, editorial, restraint, labels `/* ... */`). O site usa warm-black+vermillion — **não misturar as paletas**.
- X = **@NoctuaCore**; LinkedIn = othavioquiliao. Identidade EN canônica: "Builds terminal-native tools for developers coordinating AI agents, from Waybar telemetry to Rust token-saving CLIs." Brand source-of-truth: `othavio-site/PRODUCT.md` + `DESIGN.md`.

## Estrutura do README (final)

Hero SVG **animado** full-width servido por `othavio-site/app/api/hero` (palavra OTHAVIO com rise/ease-out-expo + onda dissolvendo o card; Geist Mono subset data-URI; fallback prefers-reduced-motion) → `/* open source */` → `/* contributions */` → 3D contrib (action `yoshi389111/github-profile-3d-contrib`: tag com prefixo `v`, `SETTING_JSON` = caminho `.github/3d-settings.json`).

## Anti-slop — removidos DE PROPÓSITO, não reintroduzir

about, stats, pinned, streak, snake, WakaTime, activity, banner gradiente, typing-svg, skill-icons marquee, footer capsule.

## Cards self-hosted

`app/api/cards/[card]/route.ts` no repo **othavio-site** (Next 16 edge, canônico www.othavio.com; GitHub GraphQL via `GH_README_TOKEN` na Vercel; só `langs` usado no README; exclui repos emach do donut — trabalho cliente). Gotcha Vercel: "Redeploy" de deploy antigo NÃO pega env var nova — deploy from source (push/commit vazio).

## Gotchas

- Next App Router: pasta iniciada com `_` = private folder (fora do roteamento) — não usar pra "rota oculta".
- Rendering de README (sem JS, camo, animação só SVG/GIF, next/og woff2→TTF): ver memória global `reference_github_readme_visuals`.
