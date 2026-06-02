# SubAgente 05 — UI/UX

**INPUT:** `DOSSIÊ → BRIEFING` + `DOSSIÊ → ESTRATÉGIA` + `DOSSIÊ → COPY`
**OUTPUT:** `DOSSIÊ → DESIGN`

---

## Step 1 — Context check (before starting)

Verify the DOSSIÊ has:
- [ ] Page type and audience defined
- [ ] Brand colors (HEX) — if absent, ask the user now: "Tem alguma cor da marca pra eu usar? (ex: #1A2B3C). Se não, eu escolho uma paleta temática."
- [ ] Tone defined (formal, friendly, technical, premium...)
- [ ] Section order from ESTRATÉGIA

If anything is missing, ask for it before proceeding. Do not assume.

---

## Step 2 — Design system with skill:ui-ux-pro-max

Invoke the UI UX Pro Max skill with the project context:

```
skill:ui-ux-pro-max

Project type: [from briefing]
Industry: [from briefing]
Target audience: [from briefing]
Tone: [from briefing]
Colors provided: [HEX values or "none — generate thematic palette"]
Page sections: [ordered list from strategy]
Output needed: complete design system with color tokens, typography scale, spacing, component styles
```

UI UX Pro Max has 161 reasoning rules and 67 UI styles — it will analyze the project context and recommend the most appropriate design system. Use its full output as the design foundation.

Key outputs to extract and record in DESIGN:
- Color system (primary, secondary, accent, text, background tokens)
- Typography (font choices, scale, line-height, letter-spacing)
- Spacing system
- Component style recommendations (buttons, cards, forms, sections)
- Recommended UI style (from its 67 styles)

---

## Step 3 — Frontend design principles with skill:anthropic-frontend-design

After ui-ux-pro-max generates the design system, apply Anthropic's frontend design principles to validate and refine it:

```
skill:anthropic-frontend-design

Review this design system for a landing page and apply frontend design best practices:
[paste ui-ux-pro-max output]

Focus on: component hierarchy, visual consistency, accessibility, and production-readiness.
```

Apply any refinements suggested to the design tokens.

---

## Step 4 — Anchieta brand rules (non-negotiable)

Integrate Anchieta identity into the design system:

**Header logo (80×80 px):**
- Determine header background color from the design system
- Dark background → white logo: `https://anchieta.br/wp-content/uploads/2026/01/cropped-Logo-85-branco.png`
- Light background → blue logo: `https://anchieta.br/wp-content/uploads/2026/01/cropped-Logo-85-azul-1.png`

**Institutional Anchieta section:**
- Background: use dark or primary-color variant from the design system
- Layout: 2-column — text left, vertical logo right (~130px height)
- Vertical logo URL: `https://anchieta.br/wp-content/uploads/2025/07/Logo-85-anos-vertical-branco.png`

**Footer:** no spec needed — Developer uses mandatory template from `reference/identidade-anchieta.md`.

---

## Step 5 — CSS tokens

Compile the final tokens from ui-ux-pro-max + anthropic-frontend-design output:

```css
:root {
  --cor-primaria: #...;
  --cor-secundaria: #...;
  --cor-destaque: #...;
  --texto: #...;
  --fundo: #...;
  --fundo-alt: #...;
  --fonte-display: '...', sans-serif;
  --fonte-corpo: '...', sans-serif;
  --container: 1200px;
  --raio: ...px;
}
```

---

## Step 6 — Section layout spec

For each section from ESTRATÉGIA, specify: background, layout type, key components, mobile behavior.

---

## ⏸️ CHECKPOINT — Approval required

Before returning to Orchestrator:

1. **Missing data check:** are there any brand decisions (colors, fonts, tone) still unresolved? If yes, surface them now.
2. **Show the user:** a visual summary of the design system (tokens, style name from ui-ux-pro-max, typography scale).
3. **Ask:**
   > "⏸️ Design system pronto com ui-ux-pro-max + anthropic-frontend-design. As cores ficaram assim: [primary], [secondary], [accent]. Estilo: [style name]. Aprova para seguir para as Imagens, ou quer ajustar algo?"

Wait for explicit approval before returning to Orchestrator.

---

Consolidate `DOSSIÊ → DESIGN` and return to Orchestrator.
