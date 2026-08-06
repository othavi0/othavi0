# othavi0 — profile README

Decisões de marca deste repo (fonte movida da memória global em 2026-07-29).

## Identidade e estilo (híbrido deliberado)

- Paleta **One Dark Pro** no README: `#21252b` bg, `#d7dae0` ink, `#abb2bf` body, `#5c6370` muted, `#e06c75` coral = **acento único**. Tipografia/voz do site othavio.com (Geist Mono, editorial, restraint, labels `/* ... */`). O site usa warm-black+vermillion — **não misturar as paletas**.
- X = **@NoctuaCore**; LinkedIn = othavioquiliao. Identidade EN canônica: "Builds terminal-native tools for developers coordinating AI agents, from Waybar telemetry to Rust token-saving CLIs." Brand source-of-truth: `othavio-site/PRODUCT.md` + `DESIGN.md`.

## Estrutura do README (final, revisada 2026-08-06)

Hero SVG **voxel animado** full-width servido por `othavio-site/app/api/hero`: OTHAVIO em cubos extrudados verde One Dark (`#98c379`, decisão do user — verde convive com o coral do resto), fundo **transparente** (funciona no GitHub dark E light), sombra projetada, cubos soltos flutuando + sheen em **SMIL loop com frame 0 completo**. NUNCA animação one-shot a partir de `opacity:0` — GitHub renderiza SVG via `<img>` congelando CSS one-shot no frame 0 (bug que deixou o hero anterior invisível; regra completa na memória global `reference_github_readme_visuals`). Sem fonte embutida — geometria pura.

Sequência: hero → `/* open source */` (3 repos: agent-bar, omarchy-noctua-theme, skills) → `/* showcase */` (grid 2×1 de previews reais via raw.githubusercontent: noctua `main`, agent-bar `master` — trocar path se preview mudar de lugar) → `/* contributions */` → 3D contrib (seção `/* languages */` com o donut foi testada e REMOVIDA a pedido do user em 2026-08-06 — não reintroduzir) (action `yoshi389111/github-profile-3d-contrib`: tag com prefixo `v`, `SETTING_JSON` = caminho `.github/3d-settings.json`).

## Anti-slop — removidos DE PROPÓSITO, não reintroduzir

about, stats, pinned, streak, snake, WakaTime, activity, banner gradiente, typing-svg, skill-icons marquee, footer capsule.

## Cards self-hosted

`app/api/cards/[card]/route.ts` no repo **othavio-site** (Next 16 edge, canônico www.othavio.com; GitHub GraphQL via `GH_README_TOKEN` na Vercel; só `langs` usado no README; exclui repos emach do donut — trabalho cliente). Gotcha Vercel: "Redeploy" de deploy antigo NÃO pega env var nova — deploy from source (push/commit vazio).

## Gotchas

- Next App Router: pasta iniciada com `_` = private folder (fora do roteamento) — não usar pra "rota oculta".
- Rendering de README (sem JS, camo, animação só SVG/GIF, next/og woff2→TTF): ver memória global `reference_github_readme_visuals`.
