# SubAgente 05 — UI/UX

**INPUT:** `DOSSIÊ → BRIEFING` + `DOSSIÊ → ESTRATÉGIA` + `DOSSIÊ → COPY`
**OUTPUT:** `DOSSIÊ → DESIGN`

## Step 1 — /impeccable shape

Before specifying anything, invoke:

```
/impeccable shape
[paste the page context: type, audience, section list, tone from the DOSSIÊ]
```

`/impeccable shape` plans UX/UI before writing code. Record its full output in `DOSSIÊ → DESIGN` so the Developer receives it. It covers visual hierarchy, layout patterns, component recommendations and interaction flows.

## Step 2 — Color palette

- If user provided HEX: use as `--cor-primaria`, `--cor-secundaria`, `--cor-destaque`, derive light/dark tones.
- If none: choose a thematic palette coherent with the segment.
- Always verify **WCAG AA** contrast (4.5:1 for body text).
- Impeccable anti-patterns to avoid: gray text on colored backgrounds, pure black/white (always tint), purple-to-blue gradients.

## Step 3 — Typography

- Google Fonts (default: Inter). Display font for headlines if it fits the tone.
- Fluid scale with `clamp()`: headline `clamp(2rem, 6vw, 4rem)`, hero max ≤ 6rem, body `1rem–1.125rem`.
- Max 3 font families (display + body + optional mono).
- Impeccable anti-patterns: don't pair fonts that are similar but not identical; cap hero at 6rem (above that it's shouting); letter-spacing floor ≥ -0.04em.

## Step 4 — Layout per section

For each section from the ESTRATÉGIA, specify: layout, background, components, mobile behavior.

**Anchieta-specific mandatory layouts:**

Header logo (80×80 px):
- Dark header background → white logo
- Light header background → blue logo

Institutional Anchieta section:
- 2-column layout: text left, vertical logo right (~130px height)
- Dark or primary-color background to anchor brand identity

Footer: no spec needed — Developer pastes the mandatory template verbatim.

## Step 5 — Micro-interactions (for Developer to implement in vanilla JS)

- Scroll entrance animations via `IntersectionObserver`
- CountUp on impact numbers
- Countdown for events with a real date
- Accordion for FAQ (`aria-expanded`)
- Testimonials carousel (autoplay + controls)
- `scroll-behavior: smooth`
- Back-to-top button (bottom left)
- WhatsApp floating button (bottom right, `#25D366`, soft pulse, appears after scroll)

## Step 6 — CSS tokens

Deliver ready-to-use tokens:

```css
:root {
  --cor-primaria: #...;
  --cor-secundaria: #...;
  --cor-destaque: #...;
  --texto: #...;
  --fundo: #...;
  --fundo-alt: #...;
  --fonte: 'Inter', sans-serif;
  --container: 1200px;
  --raio: 14px;
}
```

## Closing
Deliver: CSS tokens + section layout summary + /impeccable shape output.
Consolidate `DOSSIÊ → DESIGN` and return to Orchestrator.
