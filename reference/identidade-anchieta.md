# Identidade Visual — Grupo Anchieta

This reference is loaded once at the start of every landing page pipeline. All subagents inherit these rules. No exceptions.

---

## Logos

### Header Logo (mandatory in every page header, fixed 80×80 px)

| Background | URL |
|------------|-----|
| Dark | `https://anchieta.br/wp-content/uploads/2026/01/cropped-Logo-85-branco.png` |
| Light | `https://anchieta.br/wp-content/uploads/2026/01/cropped-Logo-85-azul-1.png` |

```html
<img
  src="[URL based on header background]"
  alt="Grupo Anchieta"
  style="width:80px;height:80px;object-fit:contain;"
/>
```

### Vertical Logo (institutional section, ~130 px height)

URL (any background): `https://anchieta.br/wp-content/uploads/2025/07/Logo-85-anos-vertical-branco.png`

```html
<img
  src="https://anchieta.br/wp-content/uploads/2025/07/Logo-85-anos-vertical-branco.png"
  alt="Grupo Anchieta — 85 anos"
  style="height:130px;width:auto;object-fit:contain;"
/>
```

---

## Institutional Section (mandatory on every page)

Every landing page must include a section about Grupo Anchieta. Minimum content:

- 85+ years of history and educational tradition
- Maximum MEC score (nota máxima)
- Commitment to professional and human excellence
- Present in [city/region — use briefing data, else `[CIDADE]`]

Position this section after the benefits block or before the FAQ — wherever it reinforces credibility best.

Layout: 2-column (text left, vertical logo right). Dark or primary-color background preferred to anchor brand identity.

---

## Mandatory Footer (paste verbatim — never modify structure, links, or logos)

The footer always has a dark background (`#0f172a`). Always use the white logo inside it.

Font Awesome must be imported in `<head>` for the social icons to render:
```html
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
```

```html
<footer style="background:#0f172a;border-top:1px solid rgba(255,255,255,0.1);font-family:'Inter',sans-serif;color:#ffffff;">
  <div style="max-width:1160px;margin:0 auto;padding:56px 20px 48px">
    <div class="lp-footer-main" style="display:grid;grid-template-columns:1fr 1fr 1fr;gap:48px;align-items:start;">
      <div style="display:flex;flex-direction:column;align-items:center;gap:12px;">
        <a href="https://anchieta.br" target="_blank" rel="noopener noreferrer" style="display:inline-block;text-decoration:none;">
          <img src="https://anchieta.br/wp-content/uploads/2026/03/Grupo-Anchieta-85-anos-Branco-Vertical-e1774625936646.png" alt="UniAnchieta" style="height:100px;width:auto;display:block;object-fit:contain;"/>
        </a>
        <p style="text-align:center;margin:0;font-size:14px;color:rgba(255,255,255,0.6);line-height:1.6;max-width:220px;">Instituição com mais de 85 anos de tradição e nota máxima no MEC.</p>
      </div>
      <div style="display:flex;flex-direction:column;align-items:center;gap:12px;">
        <span style="font-size:12px;font-weight:700;text-transform:uppercase;letter-spacing:1px;color:#ffd60a;">Credenciamento</span>
        <img src="https://anchieta.br/wp-content/uploads/2025/12/MEC-Cadastro-1-3.webp" alt="Selo E-MEC Grupo Anchieta" style="height:160px;width:auto;display:block;object-fit:contain;border-radius:10px;background:#ffffff;padding:8px;box-shadow:0 8px 30px rgba(0,0,0,0.3);"/>
        <p style="text-align:center;margin:0;font-size:14px;color:rgba(255,255,255,0.6);line-height:1.6;max-width:220px;">Consulte o cadastro da instituição no Sistema e-MEC</p>
      </div>
      <div style="display:flex;flex-direction:column;align-items:flex-end;gap:20px;">
        <span style="font-size:12px;font-weight:700;text-transform:uppercase;letter-spacing:1px;color:#ffd60a;">Redes sociais</span>
        <div style="display:flex;align-items:center;gap:12px;flex-wrap:wrap;justify-content:flex-end;">
          <a href="https://www.instagram.com/grupoanchieta/" target="_blank" rel="noopener noreferrer" aria-label="Instagram" style="width:46px;height:46px;display:inline-flex;align-items:center;justify-content:center;border-radius:50%;background:rgba(255,255,255,0.08);border:1px solid rgba(255,255,255,0.15);color:#ffffff;text-decoration:none;font-size:18px;"><i class="fa-brands fa-instagram"></i></a>
          <a href="https://www.facebook.com/GrupoAnchieta/" target="_blank" rel="noopener noreferrer" aria-label="Facebook" style="width:46px;height:46px;display:inline-flex;align-items:center;justify-content:center;border-radius:50%;background:rgba(255,255,255,0.08);border:1px solid rgba(255,255,255,0.15);color:#ffffff;text-decoration:none;font-size:18px;"><i class="fa-brands fa-facebook-f"></i></a>
          <a href="https://www.youtube.com/channel/UCvWloEtisiepLqe2htTkNdA" target="_blank" rel="noopener noreferrer" aria-label="YouTube" style="width:46px;height:46px;display:inline-flex;align-items:center;justify-content:center;border-radius:50%;background:rgba(255,255,255,0.08);border:1px solid rgba(255,255,255,0.15);color:#ffffff;text-decoration:none;font-size:18px;"><i class="fa-brands fa-youtube"></i></a>
          <a href="https://www.linkedin.com/school/unianchieta" target="_blank" rel="noopener noreferrer" aria-label="LinkedIn" style="width:46px;height:46px;display:inline-flex;align-items:center;justify-content:center;border-radius:50%;background:rgba(255,255,255,0.08);border:1px solid rgba(255,255,255,0.15);color:#ffffff;text-decoration:none;font-size:18px;"><i class="fa-brands fa-linkedin-in"></i></a>
        </div>
      </div>
    </div>
  </div>
  <div style="border-top:1px solid rgba(255,255,255,0.08);background:#0a1121;">
    <div style="max-width:1160px;margin:0 auto;padding:18px 20px;display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:12px;">
      <p style="margin:0;font-size:13px;color:rgba(255,255,255,0.5);">© 2026 Grupo Anchieta. Todos os direitos reservados.</p>
      <div style="display:flex;align-items:center;gap:8px;">
        <a href="https://anchieta.br/politica-de-privacidade" target="_blank" rel="noopener noreferrer" style="font-size:13px;color:rgba(255,255,255,0.55);text-decoration:none;">Política de Privacidade</a>
        <span style="color:rgba(255,255,255,0.2);font-size:11px;">|</span>
        <a href="https://anchieta.br/acessibilidade" target="_blank" rel="noopener noreferrer" style="font-size:13px;color:rgba(255,255,255,0.55);text-decoration:none;">Acessibilidade</a>
      </div>
    </div>
  </div>
</footer>
```
