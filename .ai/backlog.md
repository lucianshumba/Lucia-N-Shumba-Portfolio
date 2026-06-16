# Project Backlog

## Critical
_Nothing currently blocking. Site is live and functional._

---

## Important

- **Custom domain** — configure a personal domain (e.g. `luciashumba.com`) in Vercel project settings under Domains. Free SSL included. Removes dependency on the auto-generated `lucia-n-shumba-portfolio.vercel.app` subdomain.

- **Resume PDF freshness** — establish a habit: any time the CV changes, replace `resume.docx` and regenerate `resume.pdf` via the PowerShell Word COM script, then push. Consider adding a `last updated` date somewhere visible near the Download Resume button.

- **About section bio update** — the current bio paragraph was written before the Transatlantic Innovation Hub internship. Update to reflect the current role (Data & Product Design Intern, June–August 2026) and the in-progress MS at Yeshiva University's Katz School.

- **OG image social preview verification** — confirm the social card renders correctly on LinkedIn and Twitter by pasting the live URL into [opengraph.xyz](https://www.opengraph.xyz). The image is live but a real share preview test hasn't been done.

---

## Nice-to-have

- **Hero stats accuracy** — the stats (8+ years, 10 repositories, 3 domains) are hardcoded. Review periodically and update if GitHub repo count or domain count changes.

- **Mobile hamburger nav polish** — the hamburger menu works but has no close-on-outside-click behaviour. Tapping outside the open menu on mobile doesn't close it.

- **Scroll-to-top after mobile nav link** — on mobile, clicking a nav link scrolls to the section but the page position may be slightly off due to the fixed nav height. Test on a real device and add a scroll-margin-top offset if needed.

- **Project card for Zimbabwe soya bean study** — the study has a GitHub link but no live demo. If a rendered report or PDF write-up is published, link to it from the project card.

- **LinkedIn posts** — `linkedin-post.md` (portfolio launch, 3 versions) and `linkedin-internship-post.md` (internship, 3 versions) are ready locally. Version 2 of the internship post was copied to clipboard at session end for immediate posting.

- **Analytics** — add Vercel Analytics or a lightweight alternative (e.g. Plausible) to track visits and which projects get the most clicks. No tracking is currently in place.
