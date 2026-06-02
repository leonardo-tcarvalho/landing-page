# SubAgente 06 — Imagem

**INPUT:** `DOSSIÊ → BRIEFING` + `DOSSIÊ → ESTRATÉGIA` + `DOSSIÊ → COPY` + `DOSSIÊ → DESIGN`
**OUTPUT:** `DOSSIÊ → IMAGENS`

Based on the design spec, list the images the page needs and ask the user for each URL.

## Ask

> "Pelo design que montamos, a página vai precisar destas imagens. Me manda o **link direto** de cada uma (URL pública) e me diz pra que serve cada uma se quiser ajustar:
> 1. **Hero** — imagem principal do banner
> 2. **Sobre** — foto de contexto/ambiente
> 3. **Equipe / docentes** — fotos (se houver)
> 4. **Depoimentos** — rostos reais (se houver)
> 5. **Galeria** — 3+ imagens (se aplicável)
> 6. **Logos de parceiros** — (se houver)
> 7. **Favicon** — ícone da aba (opcional)"

Accept URLs in any order with notes. Validate that they look like direct image URLs (ending in `.jpg`, `.png`, `.webp`, `.svg` or from a CDN).

For missing images, record a placeholder:
- `https://placehold.co/1200x600?text=Imagem+Hero` or `[INSERIR IMAGEM: descrição]`

## For each image, record:
```
{ url, section, role, alt }
```
- `alt`: descriptive, honest, includes SEO keyword when natural.
- `loading`: `eager` for hero, `lazy` for everything below the fold.

## Closing
Summarize the image list marking which are placeholders.
Consolidate `DOSSIÊ → IMAGENS` and return to Orchestrator.

---

## ⏸️ CHECKPOINT — Approval required

Before returning to Orchestrator:

1. **Show the full output** of this subagent to the user.
2. **Check for missing data** — if anything required is absent, ask for it now before requesting approval.
3. **Ask for explicit approval:**
   > "⏸️ Imagens mapeadas. Tem [N] reais e [M] placeholders. Quer adicionar mais alguma ou aprova seguir para o SEO?"

Do NOT advance until the user confirms. If they request changes, apply them and show the updated output before asking again.

---

Consolidate the DOSSIÊ block for this subagent and return to Orchestrator.
