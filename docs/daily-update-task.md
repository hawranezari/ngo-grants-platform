# Daily update — scheduled task prompt

Schedule: every day 07:33 Europe/Copenhagen. Scope: `opps` collection only.

## Organisation policy
- No Israeli funders, funders of work in Israel, or programmes set up to support Israel or joint Israeli-Palestinian programmes. Existing matches are deleted.

## Trust rules
- Add only opportunities found on the funder's own site or an official UN/EU/government page. Listing sites
  (fundsforNGOs, opportunitydesk, developmentaid, triple-funds, jobs.ps…) are leads only.
- Never invent amounts, deadlines or eligibility ("Not published: …" when unknown).
- Never add anything that charges an application fee, comes from an unverifiable funder, or would breach UK
  sanctions / counter-terrorism law.
- New items get `review: true`; a team member confirms them in the app ("Mark as checked").
- Confirmed items get `verified: <date>` and `vsrc: <official page>`; unconfirmed items get `verify: "unconfirmed"`.

## Maintenance
- Passed deadlines → `closed` (or `upcoming` for annual calls).
- Daily re-check of open calls and deadlines within 30 days; Mondays re-check anything not verified in 30 days.

## Search order
1. Gaza/Palestine, Lebanon, Iraq (OCHA pooled funds, ECHO, EU Delegations, Irish Aid, FCDO, embassy grants, UN agencies, Taawon, Arab Fund, OPEC Fund)
2. Other Middle East & Gulf/Arab funders
3. Worldwide health/humanitarian grants open to NGOs

## Opportunity schema
`title, funder, fc (funder country), type, focus[], where, me, eligibility, intl, uk (direct|partner|check|no),
ukNote, amin, amax, acur, aNote, amount, deadline, opens, status (open|rolling|upcoming|paused|closed), url,
applyUrl, applyHow, source, notes, checked, added, review, verified, vsrc, verify`
