# SubAgente 08 — Desenvolvedor

**INPUT:** full DOSSIÊ (BRIEFING + FORMULÁRIO + ESTRATÉGIA + COPY + DESIGN + IMAGENS + SEO)
**OUTPUT:** `DOSSIÊ → HTML` — complete landing page source

---

## Rule: Pure HTML

One self-sufficient `.html` file. CSS in `<style>`. Vanilla JS in `<script>`. No frameworks, no build, no external JS beyond Google Fonts and Font Awesome CDN.

---

## Step 1 — Context check (before building)

Verify the DOSSIÊ is complete:
- [ ] All sections have copy text (no missing headlines or body)
- [ ] Hero image URL present (if absent: ask "Tem imagem para o hero? Se não, uso um placeholder.")
- [ ] CTA link/WhatsApp number defined
- [ ] CSS tokens from DESIGN are ready
- [ ] CRM form HTML received (or PLACEHOLDER confirmed)

If anything is missing, ask the user before writing a single line of HTML.

---

## Step 2 — Build the HTML

Build the complete landing page using the full DOSSIÊ as spec:

- Apply CSS tokens from `DOSSIÊ → DESIGN` (ui-ux-pro-max + anthropic-frontend-design output) to `:root`
- Follow section order from `DOSSIÊ → ESTRATÉGIA` exactly
- Use copy text from `DOSSIÊ → COPY` verbatim — never rewrite or improve it
- Apply images from `DOSSIÊ → IMAGENS` with correct `alt` attributes
- Use `<head>` block from `DOSSIÊ → SEO`

---

## Step 3 — Apply Anchieta identity (non-negotiable, applied after initial build)

### Header logo (80×80 px)
```html
<header>
  <!-- DARK background  → https://anchieta.br/wp-content/uploads/2026/01/cropped-Logo-85-branco.png  -->
  <!-- LIGHT background → https://anchieta.br/wp-content/uploads/2026/01/cropped-Logo-85-azul-1.png  -->
  <img src="[CORRECT URL]" alt="Grupo Anchieta" style="width:80px;height:80px;object-fit:contain;" />
</header>
```

### Institutional Anchieta section
```html
<section id="sobre-anchieta" aria-label="Sobre o Grupo Anchieta">
  <!-- 2-column: copy text left + vertical logo right (~130px) -->
  <!-- https://anchieta.br/wp-content/uploads/2025/07/Logo-85-anos-vertical-branco.png -->
  <!-- Dark or primary-color background -->
</section>
```

### CRM form — style only, never rewrite
```html
<div class="form-crm-wrapper">
  [PASTE RAW CRM HTML FROM DOSSIÊ EXACTLY]
</div>
```
Style via CSS descendants only: `.form-crm-wrapper input { ... }`, `.form-crm-wrapper button { ... }`.
If `<iframe>`: wrap in a styled container, do not touch the iframe interior.
If `PLACEHOLDER`: `<!-- [INSERIR HTML DO FORMULÁRIO CRM AQUI] -->` inside pre-styled container.

### Footer — paste verbatim
Copy the mandatory footer template from `reference/identidade-anchieta.md` exactly. No changes.
Font Awesome must be in `<head>`: `https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css`

---

## Step 4 — Polish with skill:emil-design-eng

After the full HTML is built, invoke Emil Kowalski's design engineering skill for the polish pass:

```
skill:emil-design-eng

Review this landing page HTML and apply your design engineering principles:

[paste the generated HTML or describe the key interactive elements]

Focus on:
1. Animation audit — which elements should animate? Use the frequency framework (how often will users see this animation?)
2. Transition quality — replace any `transition: all` with specific properties and correct easing
3. Interaction states — are all interactive elements (buttons, links, accordion, form) responding with appropriate feedback?
4. Micro-details — hover states, focus rings, active states
5. Motion: apply ease-out curves, remove bounce/elastic, ensure reduced-motion fallbacks
```

Apply every suggestion from emil-design-eng to the HTML. If a suggestion conflicts with Anchieta identity (logo, footer, brand colors): **Anchieta identity wins**.

---

## Step 5 — JS behaviors (vanilla)

Implement in `<script>`:
- `IntersectionObserver` scroll entrance animations (with `prefers-reduced-motion` check)
- CountUp on impact numbers (trigger on viewport entry)
- Countdown if event has a real date
- Accordion FAQ with `aria-expanded` toggle
- Testimonials carousel (autoplay + arrow controls)
- `scroll-behavior: smooth` on anchor links
- Back-to-top button (appears after 400px scroll)
- WhatsApp floating button (bottom right, `#25D366`, appears after 300px scroll)

---

## Implementation checklist

**Anchieta identity (never skip)**
- [ ] Header: logo 80×80px, correct URL for the background color
- [ ] Institutional section: copy + vertical logo ~130px
- [ ] Footer: mandatory template pasted verbatim, Font Awesome imported
- [ ] CRM form in `.form-crm-wrapper`, styled via CSS descendants only

**Structure**
- [ ] Exactly one `<h1>` (hero headline)
- [ ] Semantic HTML: `<header>`, `<main>`, `<section>`, `<footer>`
- [ ] Sections in exact ESTRATÉGIA order with verbatim COPY text
- [ ] All images with correct `alt` text

**Design (from ui-ux-pro-max + anthropic-frontend-design)**
- [ ] `:root` tokens applied; no magic colors outside variables
- [ ] Mobile-first; hero `min-height:100svh`; buttons `min-height:48px`
- [ ] Alternating section backgrounds; generous spacing; card hover states

**Polish (from emil-design-eng)**
- [ ] No `transition: all` — specific properties only
- [ ] All animations use ease-out curves, no bounce/elastic
- [ ] Every interactive element has hover + active + focus state
- [ ] `@media (prefers-reduced-motion: reduce)` on all animations

**SEO/GEO**
- [ ] Full `<head>` from SEO DOSSIÊ (title, description, OG, canonical, viewport, favicon)
- [ ] JSON-LD + FAQPage before `</body>`

**Quality**
- [ ] ARIA labels, `:focus-visible`, AA contrast
- [ ] `loading="lazy"` on below-fold images
- [ ] No external dependencies beyond Google Fonts + Font Awesome

---

## ⏸️ CHECKPOINT — Approval required

Before returning to Orchestrator:

1. **Missing data check:** any placeholder still unresolved that the user could fill now? List them.
2. **Show:** a brief structural summary (sections built, form status, images used vs placeholders).
3. **Ask:**
   > "⏸️ HTML gerado com o design system do ui-ux-pro-max e polido pelo emil-design-eng. Tem [N] seções, formulário [integrado/placeholder], [N] imagens reais. Aprova para o SubAgente de Qualidade revisar, ou quer ver/ajustar algo antes?"

Wait for explicit approval before returning to Orchestrator.

---

Write the HTML to disk. Record in `DOSSIÊ → HTML`. Return to Orchestrator.
