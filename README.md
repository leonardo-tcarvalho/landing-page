# landing-page

Landing page factory for Grupo Anchieta — a multi-subagent skill installable via `npx skills add`.

Works with **Kimi Code**, **Claude Code**, **Codex**, **Cursor** and [50+ other agents](https://github.com/vercel-labs/skills#supported-agents).

## Prerequisites

Install all required skills globally first:

```bash
# This skill
npx skills add your-username/landing-page -g

# UI/UX design system generation (161 rules, 67 styles)
npx skills add https://github.com/nextlevelbuilder/ui-ux-pro-max-skill --skill ui-ux-pro-max -g

# Anthropic frontend design principles
npx skills add https://github.com/openclaw/skills/tree/main/skills/qrucio/anthropic-frontend-design -g

# Emil Kowalski design engineering (animations + polish)
npx skills add https://github.com/emilkowalski/skill --skill emil-design-eng -g
```

## Usage

```
/lp
/criarLP
criar landing page para [project name]
```

## Pipeline (asks for approval at every step)

```
Orchestrator (SKILL.md)
  │  ⏸️ = waits for user approval before advancing
  │
  ├─ 01 · Briefing           ⏸️ full interview
  ├─ 02 · CRM Form           ⏸️ receives raw form HTML
  ├─ 03 · Strategy           ⏸️ approval
  ├─ 04 · Copywriter         ⏸️ approval
  ├─ 05 · UI/UX              ⏸️ skill:ui-ux-pro-max + skill:anthropic-frontend-design
  ├─ 06 · Images             ⏸️ image URLs from user
  ├─ 07 · SEO/GEO            ⏸️ approval
  ├─ 08 · Developer          ⏸️ skill:emil-design-eng polish
  ├─ 09 · Quality            ⏸️ skill:emil-design-eng review + a11y + responsive
  └─ 10 · File               → delivers .html
```

## Skills used and where

| Skill | Where | What it does |
|-------|-------|-------------|
| `skill:ui-ux-pro-max` | SubAgente 05 (UI/UX) | Generates design system with 161 rules + 67 styles |
| `skill:anthropic-frontend-design` | SubAgente 05 (UI/UX) | Validates design system with frontend best practices |
| `skill:emil-design-eng` | SubAgente 08 (Developer) | Polishes animations, transitions, interaction states |
| `skill:emil-design-eng` | SubAgente 09 (Quality) | Full Before/After design engineering review |

## Anchieta brand (enforced on every page)

| Element | Rule |
|---------|------|
| Header logo | 80×80px — white (dark bg) or blue (light bg) |
| Institutional section | Vertical logo ~130px + 85-year institutional text |
| Footer | Fixed mandatory template — never modified |
| CRM form | Raw HTML from user, styled via CSS wrapper only |

## Output

Single `.html` file — no build step, opens in any browser.

## File structure

```
landing-page/
├── SKILL.md                      ← orchestrator + approval protocol
├── openai.yaml                   ← Kimi Code interface metadata
├── README.md
├── reference/
│   └── identidade-anchieta.md    ← logos, colors, footer template
└── agents/
    ├── 01-briefing.md
    ├── 02-formulario-crm.md
    ├── 03-estrategia.md
    ├── 04-copywriter.md
    ├── 05-uiux.md                ← ui-ux-pro-max + anthropic-frontend-design
    ├── 06-imagem.md
    ├── 07-seo.md
    ├── 08-desenvolvedor.md       ← emil-design-eng polish
    ├── 09-qualidade.md           ← emil-design-eng review
    └── 10-arquivo.md
```
