# Al Risaleh Foundation — Grants & Supplies Platform

A single-page web app for a UK-registered medical and humanitarian NGO to find, apply for and track
**institutional and government funding** worldwide, with a focus on **Gaza/Palestine, Lebanon and Iraq**
and the wider Middle East.

## What's in it
| Section | What it does |
|---|---|
| Dashboard | Deadlines, applications in progress, Middle East focus, items needing a team check |
| Find grants | Opportunities by funder country, with grant size (+ £ equivalent), UK-charity eligibility, direct apply links, trust labels |
| Middle East hub | Gaza/Palestine, Lebanon and Iraq first, then Syria, Yemen, Jordan, Egypt, Türkiye; Gulf & Arab funders |
| Applications / Timeline / Applied & awarded | Workspace per application (milestones, proposal sections, documents, award tracking), CSV export |
| Funds | Funding-source directory (incl. Ireland, Gulf, Gaza/Lebanon/Iraq donors) and funder relationships |
| Medical | Supplies & equipment needs, where to get them, quality & compliance |
| Finance | Reserves, cash forecast, cost recovery, social investors |
| Organisation | Documents funders ask for; **Compliance & safety** checklist (sanctions, counter-terrorism, safeguarding, data protection, scam red flags) with official UK guidance links |

## How it runs
- `index.html` is self-contained (HTML/CSS/JS, no build step).
- It is published as a **Claude artifact**. Inside Claude it uses the artifact runtime:
  - `db` — shared team data (collections: `opps`, `apps`, `docs`, `supplies`, `settings`, `funders`)
  - `sample` — "✨ Draft with Claude" for proposal sections
  - `downloads` — CSV exports
  - `user` — signed-in identity
- Opened outside Claude (e.g. GitHub Pages or a local file) it falls back to **browser-only storage**
  (`localStorage`, prefix `ggp_`): it works, but data is not shared and the opportunity list starts empty.

**The team's data lives in the artifact database, not in this repository.** This repo holds the app code
and documentation only. No secrets or personal data are stored here.

## Test version (for sharing outside Claude)
`test-site/` is a standalone copy for testers: the opportunity list is built in (snapshot), anything a tester
enters stays in their own browser, and a **Give feedback** form sends answers to Netlify Forms.
Deploy it by dragging `test-site/` (or the zip) onto the Netlify project's Deploys page.
It is marked `noindex` so search engines don't list it.

## Daily update
A Claude scheduled task runs every day at 07:33 (Europe/Copenhagen) and maintains the `opps` collection only.
Its rules are in [`docs/daily-update-task.md`](docs/daily-update-task.md): official sources only, never invent
amounts or deadlines, flag new items `review: true` for a human check, re-verify open calls daily and
everything else weekly.

## Sharing with colleagues
Share the artifact from claude.ai (Share → invite by email). "Can edit" = can track applications and tick
checklists; "view only" = read-only. Pushing this repo does **not** share the live tool or its data.

## Disclaimer
Funding information changes often — always confirm deadlines, amounts and eligibility on the funder's own
page before applying. The compliance checklist is practical guidance, not legal advice.
