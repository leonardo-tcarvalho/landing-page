# landing-page

Landing page factory for Grupo Anchieta — a multi-subagent skill installable via `npx skills add`.

Works with **Kimi Code**, **Claude Code**, **Codex**, **Cursor**, **OpenCode** and [50+ other agents](https://github.com/vercel-labs/skills#supported-agents).

## Install

```bash
# Install globally (available in all projects)
npx skills add your-username/landing-page -g

# Or project-local
npx skills add your-username/landing-page
```

> **Prerequisite:** [Impeccable](https://github.com/pbakaus/impeccable) must be installed in your agent:
> ```bash
> npx skills add pbakaus/impeccable -g
> ```

## Usage

Once installed, trigger it with any of these in your agent:

```
/lp
/criarLP
criar landing page
criar uma LP para [project name]
```

## What it does

Runs a pipeline of 10 specialist subagents that build a production-ready HTML landing page:

```
Orchestrator (SKILL.md)
  │
  ├─ 01 · Briefing        → collects project context from user
  ├─ 02 · CRM Form        → receives raw CRM form HTML from user
  ├─ 03 · Strategy        → positioning, sections, conversion triggers
  ├─ 04 · Copywriter      → all section texts + Anchieta institutional copy
  ├─ 05 · UI/UX           → /impeccable shape + CSS design tokens
  ├─ 06 · Images          → image URLs and alt text from user
  ├─ 07 · SEO/GEO         → full <head> + JSON-LD Schema + GEO optimization
  ├─ 08 · Developer       → /impeccable craft + typeset + layout + animate
  ├─ 09 · Quality         → npx impeccable detect + /audit + /polish
  └─ 10 · File            → saves .html and delivers
```

## Impeccable integration

| Subagent | Command | Purpose |
|----------|---------|---------|
| UI/UX | `/impeccable shape` | Plans UX/UI before any code |
| Developer | `/impeccable craft` | Builds HTML with all 7 design refs loaded |
| Developer | `/impeccable typeset` | Fixes typography hierarchy |
| Developer | `/impeccable layout` | Fixes spacing and visual rhythm |
| Developer | `/impeccable animate` | Adds purposeful motion |
| Quality | `npx impeccable detect` | Catches 24 anti-patterns (no LLM) |
| Quality | `/impeccable audit` | A11y + performance + responsive check |
| Quality | `/impeccable polish` | Final design pass |

## Anchieta brand rules (enforced on every page)

| Element | Rule |
|---------|------|
| Header logo | 80×80px — white (dark bg) or blue (light bg) |
| Institutional section | Vertical logo ~130px + 85-year institutional text |
| Footer | Fixed mandatory template — never modified |
| CRM form | Raw HTML from user, styled via CSS wrapper only |

## Output

A single `.html` file — no build step, no dependencies, opens directly in any browser.

## File structure

```
landing-page/
├── SKILL.md                      ← orchestrator + global rules
├── openai.yaml                   ← Kimi Code interface metadata
├── README.md
├── reference/
│   └── identidade-anchieta.md    ← logos, colors, footer template
└── agents/
    ├── 01-briefing.md
    ├── 02-formulario-crm.md
    ├── 03-estrategia.md
    ├── 04-copywriter.md
    ├── 05-uiux.md
    ├── 06-imagem.md
    ├── 07-seo.md
    ├── 08-desenvolvedor.md
    ├── 09-qualidade.md
    └── 10-arquivo.md
```

## License

MIT
