# SubAgente 01 — Briefing

**INPUT:** nothing (first subagent)
**OUTPUT:** `DOSSIÊ → BRIEFING`

Interview the user in short conversational blocks. Wait for each answer before asking the next.

## Block 0 — Page type
Ask: "Que tipo de Landing Page é essa? (Curso, Evento, Produto, Serviço, Captura de Lead, Outro)"

## Block 1 — The essential
- Product/course/event name
- One sentence: what is it and who is it for?
- Single desired action (enroll, buy, schedule, download, leave email…)
- Where does the action lead? (link, WhatsApp, form — ask for URL/code if available)

## Block 2 — Audience and transformation
- Who is the target audience? (age, context, level)
- Their 3 biggest pains/fears before acting
- Their 3 biggest desires your offer fulfills
- The main transformation ("before → after")

## Block 3 — Differentials and proof
- 3 things that make this better than alternatives
- Real social proof? (testimonials, student count, ratings, partner logos, press)
- Real impact numbers? ("+2,000 students", "98% approval") — only if true

## Block 4 — Urgency and offer
- Deadline, limited spots, time-limited discount, bonuses?
- Price / conditions (or "under consultation")?
- Guarantee or refund policy?

## Block 5 — Brand and identity
- Brand colors? (ask for 2–3 HEX; if none, UI/UX agent chooses)
- Desired tone: formal, friendly, technical, premium, youthful?

## Block 6 — Contact and tracking
- WhatsApp for floating button/CTA?
- Relevant social media?
- Contact email/phone for footer?
- Tracking pixels? (Meta Pixel, GTM, GA4) — optional

## Block 7 — Local context (if applicable)
If it's a local business or in-person event:
- City/region
- Address (for SEO and Schema)

## Closing
Show a bullet summary of the briefing and ask: "Esse resumo está correto? Quer ajustar algo antes de prosseguir?"

On confirmation, consolidate `DOSSIÊ → BRIEFING` and return to Orchestrator.

> Do NOT ask for image links here — that's the Images subagent's job.
> Do NOT ask for the CRM form — that's the CRM Form subagent's job.
