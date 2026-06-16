# Key Decisions

## 2026-06-16 — Single-file static site (no framework)

**Decision:** Build the entire portfolio as one `index.html` with embedded CSS and JavaScript. No React, no Next.js, no build step.

**Reason:** A personal portfolio has no dynamic data requirements. A single file is trivially deployable anywhere, has zero dependency rot, and loads instantly. The complexity budget is better spent on design polish than on framework scaffolding.

**Impact:** All future edits are direct HTML/CSS edits. No `npm install`, no build pipeline to maintain.

**Reversal:** If the site grows significantly (blog, CMS, dynamic project data), migrate to Next.js static export — the design tokens and component structure map cleanly.

---

## 2026-06-16 — Navy/gold dark design system

**Decision:** Navy (#0D1B2A) primary background, gold (#C9A84C) accent, Playfair Display serif for headings, Inter for body, JetBrains Mono for labels/code.

**Reason:** Reflects a professional, senior-level aesthetic appropriate for a data scientist. The serif/sans/mono typographic stack communicates both analytical credibility and design intentionality. Dark theme reduces visual noise.

**Impact:** All future UI additions must use the defined CSS custom properties (`--navy`, `--gold`, etc.). The OG image (`gen_og.py`) hardcodes the same palette — update both if the design system changes.

**Reversal:** Swap CSS custom property values at the `:root` level; regenerate `og-image.png`.

---

## 2026-06-16 — GitHub → Vercel deployment (not Vercel CLI)

**Decision:** Connect the GitHub repo to Vercel via the dashboard import flow rather than using the Vercel CLI directly.

**Reason:** Auto-deploy on every `git push` to `main` is more durable than a CLI-based workflow. No local Vercel CLI dependency. Standard workflow: edit → commit → push → deployed.

**Impact:** Every push to `main` triggers a production redeploy. No staging environment configured.

**Reversal:** Install Vercel CLI (`npm i -g vercel`) for preview deployments or if the GitHub integration needs to be replaced.

---

## 2026-06-16 — OG image generated via Python + Pillow (not a hosted service)

**Decision:** Generate `og-image.png` programmatically with Python 3 + Pillow using `gen_og.py`, committed as a static PNG.

**Reason:** Avoids dependency on third-party OG image services (which can go down, charge fees, or require API keys). The image is committed to the repo and served as a plain static file — zero runtime cost.

**Impact:** When hero text changes (e.g. title update), `gen_og.py` must be re-run and `og-image.png` re-committed. `gen_og.py` is not committed to the repo (kept local).

**Reversal:** Replace with a Vercel OG image API route (`@vercel/og`) if dynamic generation becomes necessary.

---

## 2026-06-16 — Resume PDF via Microsoft Word COM (not LibreOffice)

**Decision:** Convert `resume.docx` to `resume.pdf` using PowerShell + Microsoft Word 16 COM automation rather than LibreOffice.

**Reason:** LibreOffice was not installed. Word COM was available (Microsoft 365, version 16) and produces higher-fidelity PDF output that preserves the original `.docx` formatting exactly.

**Impact:** PDF regeneration requires a Windows machine with Word installed. The `.docx` source file is intentionally not committed to the public repo.

**Reversal:** Install LibreOffice and use `soffice --headless --convert-to pdf resume.docx` for a cross-platform alternative.

---

## 2026-06-16 — Section numbering convention

**Decision:** Sections are labeled `// 01 — About` through `// 06 — Contact` using JetBrains Mono in gold.

**Reason:** Reinforces the "technical/analytical" aesthetic and gives the page a clear visual rhythm. The `//` prefix references code comment syntax — appropriate for a data scientist's portfolio.

**Impact:** Adding or removing sections requires renumbering subsequent labels. Education (// 04) was inserted between Experience and Skills in this session, shifting Skills to // 05 and Contact to // 06.
