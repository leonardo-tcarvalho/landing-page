# SubAgente 08 — Desenvolvedor

**INPUT:** full DOSSIÊ (BRIEFING + FORMULÁRIO + ESTRATÉGIA + COPY + DESIGN + IMAGENS + SEO)
**OUTPUT:** `DOSSIÊ → HTML` — complete landing page source

---

## Rule: Pure HTML

One self-sufficient `.html` file. CSS in `<style>`. Vanilla JS in `<script>`. No frameworks, no build, no external JS beyond Google Fonts and Font Awesome CDN.

---

## Step 1 — Build with /impeccable craft

Invoke with the full DOSSIÊ as context:

```
/impeccable craft

Page type: [from briefing]
Audience: [from briefing]
CSS tokens: [from design]
Section order: [from strategy]
Copy: [from copy]
Images: [from images]
/impeccable shape output: [from design]

Constraints:
- Pure HTML, single file, no frameworks
- Mobile-first (375px base)
- WCAG AA
- All copy from the DOSSIÊ — do not rewrite or improve it
```

`/impeccable craft` runs the full shape→build flow with all 7 design references loaded (typography, color-and-contrast, spatial-design, motion-design, interaction-design, responsive-design, ux-writing). Use the resulting HTML as the base.

---

## Step 2 — Apply Anchieta identity (non-negotiable)

After craft output, apply these rules over the generated HTML:

### Header logo (80×80 px)
```html
<header>
  <!-- Choose URL based on header background color:
       DARK  → https://anchieta.br/wp-content/uploads/2026/01/cropped-Logo-85-branco.png
       LIGHT → https://anchieta.br/wp-content/uploads/2026/01/cropped-Logo-85-azul-1.png -->
  <img
    src="[CORRECT URL]"
    alt="Grupo Anchieta"
    style="width:80px;height:80px;object-fit:contain;"
  />
</header>
```

### Institutional Anchieta section
```html
<section id="sobre-anchieta" aria-label="Sobre o Grupo Anchieta">
  <!-- 2-column layout: copy text (left) + vertical logo ~130px (right) -->
  <!-- Vertical logo: https://anchieta.br/wp-content/uploads/2025/07/Logo-85-anos-vertical-branco.png -->
  <!-- Dark or primary-color background -->
</section>
```

### CRM form
Take the raw HTML from `DOSSIÊ → FORMULÁRIO`:
- Wrap it in `<div class="form-crm-wrapper">`
- Style **only via CSS** with descendant selectors: `.form-crm-wrapper input`, `.form-crm-wrapper button`, etc. — matching the page's palette, typography, border radius and button color
- **Never rewrite or alter the CRM code**
- If `<iframe>`: wrap in a styled container, do not touch the iframe interior
- If `PLACEHOLDER`: `<!-- [INSERIR HTML DO FORMULÁRIO CRM AQUI] -->` inside the pre-styled container

### Footer
Paste the mandatory footer **exactly** from `reference/identidade-anchieta.md`. No structural changes, no link changes, no logo changes.

Font Awesome must be in `<head>`:
```html
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
```

---

## Step 3 — Impeccable refinements

Apply targeted commands over the complete HTML:

```
/impeccable typeset
```
Fix typography hierarchy, sizes and font choices.

```
/impeccable layout
```
Fix spacing, grid rhythm, visual breathing room.

```
/impeccable animate
```
Add purposeful motion (IntersectionObserver, CountUp, smooth transitions, reduced-motion fallbacks).

Apply each suggestion. If any refinement conflicts with Anchieta identity (logos, footer, brand colors) — **Anchieta identity wins**.

---

## Implementation checklist

**Anchieta identity (never skip)**
- [ ] Header: Anchieta logo 80×80px, correct URL for the header background
- [ ] Institutional section: copy text + vertical logo ~130px
- [ ] Footer: mandatory template pasted verbatim, Font Awesome imported
- [ ] CRM form in `.form-crm-wrapper`, styled via CSS only

**Structure**
- [ ] Exactly one `<h1>` (hero headline)
- [ ] Semantic HTML: `<header>`, `<main>`, `<section>`, `<footer>`
- [ ] Sections in exact ESTRATÉGIA order with COPY text (never rewrite copy)
- [ ] All images with correct `alt` text

**Design (from impeccable craft + refinements)**
- [ ] `:root` tokens applied; no magic colors outside variables
- [ ] Mobile-first; hero `min-height:100svh`; buttons `min-height:48px`
- [ ] Alternating section backgrounds; generous spacing; card hover states

**SEO/GEO**
- [ ] Full `<head>` from SEO DOSSIÊ (title, description, OG, canonical, viewport, favicon)
- [ ] JSON-LD + FAQPage before `</body>`

**Quality**
- [ ] ARIA labels, `:focus-visible`, AA contrast
- [ ] `loading="lazy"` on below-fold images
- [ ] No external dependencies beyond Google Fonts + Font Awesome

---

## Closing

Write the complete HTML file to disk — do not paste it entirely in chat.
Record in `DOSSIÊ → HTML`.
Return to Orchestrator: "HTML gerado, pronto para validação pelo SubAgente de Qualidade."
