# othavi0, profile README

Decisões de marca deste repo. Revisado em 2026-10-21.

## Identidade e estilo

- Voz do README: Geist Mono, editorial, contido, títulos de seção em `/* ... */`. Fonte de voz e produto: `PRODUCT.md` e `DESIGN.md` no repo **othavio-site** (o domínio othavio.com saiu do ar, os docs continuam valendo).
- Paleta **One Dark Pro** nas peças geradas (3D em `.github/3d-settings.json`, theme noctua). Não misturar com o warm-black e vermillion do antigo othavio.com.
- Links canônicos: site **www.noctuacore.com**, X **@noctuacore** (`x.com/noctuacore`), LinkedIn **othavioquiliao**.
- Identidade EN: "Builds terminal-native tools for developers coordinating AI agents." Vai no `alt` do hero.

## Estrutura do README (revisada 2026-10-21)

Sequência: hero, linha de links, `/* open source */`, `/* showcase */`, `/* contributions */`, 3D.

- **Hero**: SVG voxel animado servido por `www.noctuacore.com/api/hero`, código em `apps/web/src/app/api/hero/route.ts` do repo **noctuacore**. OTHAVIO em cubos azul aço (`#5c7e9e`), fundo transparente (funciona no GitHub claro e escuro), sombra projetada, cubos soltos e sheen em **SMIL loop com frame 0 completo**. NUNCA animação one-shot a partir de `opacity:0`: o GitHub renderiza SVG via `<img>` e congela CSS one-shot no frame 0. Sem fonte embutida, só geometria.
- **Links**: noctuacore.com, x.com/noctuacore e linkedin, centralizados abaixo do hero.
- **Open source** (4, numerados `01` a `04`): omarchy-agent-bar, omanotes, omarchy-noctua-theme, noctua-skills.
- **Showcase**: grade de 3 colunas. noctua e agent-bar via raw.githubusercontent (noctua `main/preview.png`, agent-bar `master/preview.png`). omanotes usa `assets/omanotes.png` deste repo, print escolhido pelo user. Trocar o path se um preview mudar de lugar.
- **Contributions** (4, cada linha com link para o PR): herdr #25, mission-control #102, omadoro (5 PRs), svelte-animations #9 e #34. Só PR com merge entra.
- **3D**: action `yoshi389111/github-profile-3d-contrib` (tag com prefixo `v`, `SETTING_JSON` = `.github/3d-settings.json`). Regenera todo dia e faz commit na main, então branch de README faz rebase antes do push.

## Removidos de propósito, não reintroduzir

- about, stats, pinned, streak, snake, WakaTime, activity, banner gradiente, typing-svg, skill-icons marquee, footer capsule.
- `/* languages */` com o donut (removido 2026-08-06).
- `/* lab */` com repos privados sem link (recusado 2026-10-21): só projeto público entra.
- Contribuições workspace-lens e omatodolist (decisão do user em 2026-10-21) e rtk #1768 (fechou sem merge).

## Gotchas

- Next App Router: pasta iniciada com `_` é private folder (fora do roteamento). Não usar para "rota oculta".
- Vercel: "Redeploy" de deploy antigo NÃO pega env var nova. Fazer deploy from source (push ou commit vazio).
- Rendering de README: o GitHub não roda JS e serve toda imagem pelo proxy camo; animação só em SVG (SMIL) ou GIF. No `next/og`, fonte em TTF, não woff2.
- Para conferir o render sem publicar: `gh api /markdown` com `mode=gfm` e `context=othavi0/othavi0`.
