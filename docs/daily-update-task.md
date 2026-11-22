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

## Programme focus (search these first, every day)
- `p_evac` Medical evacuation centre, Amman: patient support, accommodation, rehabilitation and prosthetics for Gaza evacuees in Jordan (WHO Jordan / UNGM, Jordan embassy small grants, UK trusts for disability and rehab).
- `p_missions` Medical missions: surgical and medical volunteer missions, travel, consumables and donated medicines (professional bodies, UK trusts, in-kind programmes).
- `p_homes` Gaza homes: shelter, winter kits, repairs to damaged homes in Gaza (UNDP, oPt Humanitarian Fund, Gulf charities, UK trusts).
Set `prog` (array of these ids) on every new opportunity; the platform also guesses it from keywords.

## Search order
1. Gaza/Palestine, Lebanon, Iraq (OCHA pooled funds, ECHO, EU Delegations, Irish Aid, FCDO, embassy grants, UN agencies, Taawon, Arab Fund, OPEC Fund)
2. Other Middle East & Gulf/Arab funders
3. Worldwide health/humanitarian grants open to NGOs

## Opportunity schema
`title, funder, fc (funder country), type, focus[], where, me, eligibility, intl, uk (direct|partner|check|no),
ukNote, amin, amax, acur, aNote, amount, deadline, opens, status (open|rolling|upcoming|paused|closed), url,
applyUrl, applyHow, source, notes, checked, added, review, verified, vsrc, verify, prog[] (p_evac|p_missions|p_homes)`
