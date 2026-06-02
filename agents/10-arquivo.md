# SubAgente 10 — Arquivo

**INPUT:** `DOSSIÊ → HTML` (validated by Quality) + full DOSSIÊ (for the summary)
**OUTPUT:** `.html` file saved to disk and delivered to user

---

## Steps

1. **Name the file** — descriptive slug from the project name:
   - "Pós em Data Science" → `landing-page-pos-data-science.html`
   - No spaces, no accents, lowercase, hyphen-separated.

2. **Save the file** to the output directory:
   - Path: `/mnt/user-data/outputs/<slug>.html` (or current project dir)
   - Content: the complete HTML from `DOSSIÊ → HTML`, exactly as validated.

3. **Sanity check:**
   - Starts with `<!DOCTYPE html>`, ends with `</html>`
   - Has `<title>`, exactly one `<h1>`, JSON-LD block
   - Has Anchieta header logo (80×80px)
   - Has institutional Anchieta section
   - Has mandatory footer template
   - Has `.form-crm-wrapper` with CRM form (or placeholder)
   - No external dependencies beyond Google Fonts + Font Awesome

4. **Deliver** with `present_files` pointing to the saved file.

5. **Write a delivery summary:**

```
✅ Sua Landing Page está pronta!
É um arquivo HTML único — abra com duplo clique em qualquer navegador ou hospede onde quiser.

O que entrou:
- Seções: [list in order]
- Impeccable: /craft → /typeset → /layout → /animate → detect → /audit → /polish
- SEO/GEO: title + meta description + Open Graph + Schema [type] + FAQPage
- Identidade Anchieta: logo no header, seção institucional, footer padrão
- Formulário: [CRM embedded + styled / PLACEHOLDER]
- Imagens: [N real, M placeholders]

Pendências para você:
- Substituir placeholders de imagem: [list]
- Inserir código de tracking: [Meta Pixel / GTM if pending]
- Confirmar link/endpoint do formulário

Quer que eu ajuste cores, reescreva alguma seção ou crie uma variação? É só pedir.
```

---

## Notes

- Document any dossiê gaps clearly in the pending section.
- If the user requests separate CSS/JS files afterward, accommodate — but the default is single HTML file.
- Pipeline complete. Orchestrator may offer iteration.

---

## ⏸️ CHECKPOINT — Approval required

Before returning to Orchestrator:

1. **Show the full output** of this subagent to the user.
2. **Check for missing data** — if anything required is absent, ask for it now before requesting approval.
3. **Ask for explicit approval:**
   > "⏸️ Arquivo salvo e pronto para entrega."

Do NOT advance until the user confirms. If they request changes, apply them and show the updated output before asking again.

---

Consolidate the DOSSIÊ block for this subagent and return to Orchestrator.
