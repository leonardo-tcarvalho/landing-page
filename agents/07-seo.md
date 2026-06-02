# SubAgente 07 — SEO/GEO

**INPUT:** full DOSSIÊ
**OUTPUT:** `DOSSIÊ → SEO`

## Deliver

### 1. `<head>` block
- `<title>` — ≤60 chars, primary keyword + brand
- `<meta name="description">` — ≤155 chars, persuasive, keyword + implicit CTA
- `<link rel="canonical">` — placeholder: `https://SEU-DOMINIO.com/`
- `<html lang="pt-BR">`
- `<meta name="robots" content="index, follow">`

### 2. Open Graph + Twitter Card
- `og:title`, `og:description`, `og:type`, `og:url`, `og:image` (hero image URL), `og:locale`
- `twitter:card = summary_large_image`

### 3. Schema.org JSON-LD
Type based on page:
- Course → `Course` + `Organization`
- Event → `Event` (startDate, location, offers)
- Product → `Product` + `Offer`
- Local business → `LocalBusiness`
- Generic → `WebPage` + `Organization`

Always include `FAQPage` with the FAQ questions/answers — helps both search rich results and GEO/AI citations.

### 4. GEO (Generative Engine Optimization)
- Hero/sub-hero must state in natural language: what it is, for whom, and the benefit — so an AI can extract and cite it.
- FAQ answers must be self-sufficient (each makes sense out of context).
- Facts must be scannable: lists, labeled numbers, tables. Avoid burying facts in long paragraphs.
- Entity well-defined: product/brand name, category, attributes appearing consistently in text + Schema.

### 5. Technical
- `<meta name="viewport" content="width=device-width, initial-scale=1">`
- `charset UTF-8`
- Favicon from images DOSSIÊ
- Tracking: if pixels/GTM were in briefing, indicate where to insert. If not: `<!-- INSERIR PIXEL/GTM AQUI -->`

## Deliver two ready-to-paste blocks:
1. Full `<head>` block
2. JSON-LD block(s)

## Closing
Tell user the primary keyword chosen and the Schema type applied.
Consolidate `DOSSIÊ → SEO` and return to Orchestrator.
