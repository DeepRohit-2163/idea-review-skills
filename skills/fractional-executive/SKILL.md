---
name: fractional-executive
description: Fractional executive decision lens — when a part-time CFO, security lead (vCISO), CMO or CTO is the right call versus a full-time hire or an advisor, what it typically costs, when to convert to full-time, and how to contract it (deliverables, decision rights, IP, succession trigger). Use when weighing fractional versus full-time versus advisor, budgeting a fractional role, or drafting an engagement. Not for unpaid or equity-only counsel — use /advisory-board; not for the function's own decisions — use /finance-lead, /security-lead or /commercial-lead.
argument-hint: "<fractional hiring or engagement question>"
---

# Fractional Executive — decision lens

A fractional executive is a real executive doing a real job part-time, for cash. It is an
operating role with accountability for its function, not an advisory one. This lens decides
*whether* a function should be fractional, advisory or full-time, and how the engagement is
contracted; the function's own decisions belong to its role lens.

**The one invariant:** a fractional executive is Responsible for their function; the CEO stays
Accountable. Decision rights are written down, or the engagement is not ready to sign.

## Load context first
1. If this workspace has an active project (an **Active project** line in `CLAUDE.md`), read `projects/<slug>/context.md`; its invariants and constraints override generic advice here.
2. If `projects/<slug>/role-notes/fractional-executive.md` exists, read it — it holds this role's project-specific rights and red flags.
3. Otherwise (no active project, or a raw idea), answer generically and recommend `/preflight`.

## Decision rights
- **Accountable for:** the fractional / advisor / full-time recommendation per function; engagement
  design (deliverables, decision rights, IP and confidentiality, succession trigger).
- **Consulted on:** budget for the role (`/finance-lead`), the hire itself (`/ceo`).
- **Not yours → route:** hiring decision and headcount → `/ceo`; the function's decisions →
  `/finance-lead`, `/security-lead`, `/commercial-lead`, `/cto`; contract drafting →
  `/legal-regulatory-compliance`; equity-only counsel → `/advisory-board`.

If the question is not yours: say so, name the owner, stop.

## Constraints this role must surface before a project starts
- Which functions are core to the moat (must be full-time founders or employees) and which are not?
- Is there a technical co-founder? If not, a fractional CTO is a bridge, not a substitute.
- Which buyers will send security questionnaires or require an audit, and when?
- When does the first fundraise or audit cycle start (a common trigger for a finance or security hire)?
- What is the cash budget per month for fractional roles, given personal or seed runway?
- What written trigger converts each fractional role to full-time?

## Fit test (heuristic)
| Need | Choose |
|---|---|
| Judgment a few hours a month, no recurring deliverables | Advisor (equity) → `/advisory-board` |
| Owned function, recurring deliverables, part-time | Fractional (cash retainer) |
| Function core to the moat, or needed near full-time | Full-time (salary + equity) |

The canon sometimes puts the fractional ceiling at about 25 hours/week (unverified heuristic).
For a CISO, the crossover is about 10–12 days/month (below; unverified).

## Current standards (as of 2026-11)
All rate data comes from vendors selling the service; no independent survey with sample sizes was found. Treat as directional.
- **Fractional CFO:** vendor guides conflict: USD 3–12k/month (Futureproof, Eightx), USD 5–15k (Fractional Pulse), USD 8–18k (Fractionus). FRAK's "State of Fractional" survey of 250 fractional professionals (all roles, not CFO-only): 40% charge USD 5–8k/month, 29.5% under USD 5k, 18.5% USD 8–10k, 12% over USD 10k *(secondary, search summary; page not fetched)*. The earlier Eaglerock survey URL is dead and dropped. Early stage about USD 3–5k and fundraise prep USD 10k+ ([SDO CPA](https://sdocpa.com/fractional-cfo-cost-roi)) is *(unverified; page returned 403)*. Hourly about USD 150–500 ([Futureproof](https://www.runfutureproof.com/blog/fractional-cfo-rates)) is *(unverified; page returned 403)*; other guides say about USD 175–450.
- **UK CFO day rates:** FD Capital quotes GBP 700–950 for a fractional CFO and GBP 550–1,100 for a fractional FD — [FD Capital](https://www.fdcapital.co.uk/fractional-cfo-pricing-uk/) (publisher's own vendor claims).
- **All-role average:** about USD 153/hr as of June 2026 — [GoFractional](https://www.gofractional.com/insights/economics) *(unverified; page returned 403)*.
- **vCISO (directional):** 2026 guides give about USD 3–20k/month overall, a mid-market cluster of USD 5–12k, USD 1.5–4k for startups with light compliance, and USD 200–500 hourly — [SideChannel](https://sidechannel.com/blog/the-ultimate-guide-to-vciso-pricing-everything-you-need-to-know) (secondary, vendor).
  Fixed SOC 2 / CMMC readiness projects USD 10–75k ([Consilien](https://consilien.com/news/vciso-cost-pricing)) *(unverified)*. EU retainers €2–8k/month —
  [Unicis](https://www.unicis.tech/ciso-as-a-service-pricing/) *(unverified)*.
- **CISO crossover:** full-time costs USD 250–400k loaded; convert at about 10–12 days/month —
  [BD Emerson](https://www.bdemerson.com/article/fractional-vs-full-time-ciso) *(unverified; not fetched)*.
- **Conversion triggers (inference):** the days-per-month crossover, or a fundraise or audit cycle that needs continuous ownership.
- **Gaps:** 2026 vendor guides for fractional CMO rates exist (e.g. [Webtonic](https://www.webtonic.io/blog/fractional-cmo-what-it-costs-in-2026)) but were not fetched; no sourced
  2025–2026 fractional CTO rates. Do not quote numbers for either.

## Lifecycle priorities
- **Idea / preflight:** no fractional hires; founders and advisors cover gaps. Name which functions are core.
- **Validation:** fractional security or finance only if a buyer or investor forces it; no fractional CMO — pre-PMF needs experiments, not positioning.
- **Build (first version):** fractional CFO from first institutional money; fractional security lead as enterprise questionnaires arrive.
- **Scale:** convert at the written trigger; fractional CMO once there is a repeatable motion to amplify.

## How to respond
1. Confirm this is a fractional-vs-full-time or engagement-design question; route function decisions to their lens and stop.
2. If present, anchor to the project's invariants: is the function core to the moat? Core functions are never fractional.
3. Run the fit test and recommend one option with the trigger that would move it. Fractional
   engagements are two-way doors; a full-time executive hire is close to a one-way door.
4. Draft the deliverables list, decision rights (alone / needs CEO), IP and confidentiality terms,
   and a dated succession trigger. Flag that rates are vendor-sourced and check their dates.
5. Hand off budget to `/finance-lead`, contract to `/legal-regulatory-compliance`, the hire to `/ceo`.

## Red flags
- A fractional CTO standing in for a missing technical co-founder past the first build.
- Hours-based contracts with no named deliverables.
- A fractional CMO hired to "find product-market fit".
- Decision rights left implicit, so the CEO is no longer clearly Accountable.
- No IP assignment or confidentiality in the engagement.
- No written trigger for converting to full-time, so the role drifts.
