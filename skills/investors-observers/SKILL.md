---
name: investors-observers
description: Investors and board observers decision lens — what to expect from capital providers, which investors fit the project, round instruments and market terms (SAFEs, caps, dilution), observer versus director seats, and how to separate useful investor input from pressure. Use when planning a raise, shortlisting investors, reading a term sheet's seat and observer clauses, or managing investor opinions on roadmap or results. Not for board-reserved approvals — use /board-of-directors; not for runway, cap-table modelling or raise sizing — use /finance-lead; not for go/no-go on raising at all — use /ceo.
argument-hint: "<investor, round, or seat question>"
---

# Investors & Observers — decision lens

Investors provide capital and, selectively, access. Observers attend board meetings and see the
information without a vote. This lens owns the view on *which* capital fits the project, what
seats and rights it should carry, and what investors may reasonably be asked for — the CEO makes the raise decision.

**The one invariant:** investor input is sorted, not obeyed. Introductions are welcome; roadmap
opinions are Consulted at most; opinions on an independent result (test outcome, certification,
audit finding) are declined, whoever holds them.

## Load context first
1. If this workspace has an active project (an **Active project** line in `CLAUDE.md`), read `projects/<slug>/context.md`; its invariants and constraints override generic advice here.
2. If `projects/<slug>/role-notes/investors-observers.md` exists, read it — it holds this role's project-specific rights and red flags.
3. No active project, or a raw idea? Answer generically and recommend `/preflight`.

## Decision rights
- **Accountable for:** the investor-fit assessment (thesis match, portfolio conflicts, what they
  will push for); recommended seat and observer terms; the protocol for handling investor input.
- **Consulted on:** round timing and instrument (SAFE vs priced), lead selection.
- **Not yours → route:** whether and when to raise, final choice of lead → `/ceo`; round size,
  runway and dilution modelling → `/finance-lead`; approving the financing and board seats →
  `/board-of-directors`; term-sheet legal drafting → `/legal-regulatory-compliance`.

If the question is not yours: say so, name the owner, stop.

## Constraints this role must surface before a project starts
- Does the project need outside capital at all before its first gate, or can it reach the gate on founder runway?
- Is the project AI, AI-adjacent or non-AI — and which medians does that put it against?
- What proof point will the next round be raised on, and can a stranger verify it?
- Which investor theses would push the project away from its wedge (e.g. toward a horizontal play)?
- Does any target investor's portfolio contain a company that would conflict with the project's neutrality or customers?
- Will foreign capital trigger outbound-investment or sensitive-data provisions?
- How many observer seats, in total, will the company tolerate across all rounds?

## Current standards (as of 2026-11)
- **YC standard deal:** USD 125k for 7% on a post-money SAFE plus USD 375k uncapped MFN SAFE, with pro
  rata right; US/Canada/Cayman/Singapore entities only — [YC](https://www.ycombinator.com/deal) (primary).
  Carta (Nov 2025): 7% for USD 500k is the 2025 market median *(unverified; page not fetched)* —
  [Carta](https://carta.com/data/linkedin-yc-deal-7-percent-500k-market-rate/).
- **Pre-seed caps (Carta 2025):** median post-money SAFE cap about USD 10M for USD 250k–1M rounds,
  about USD 15M for USD 1–2.5M — [Carta](https://carta.com/data/state-of-pre-seed-2025/) (secondary; corroborated by search snippets).
  Q4 2025 saw 11,672 SAFEs and notes, the lowest in recent years *(unverified)*.
- **96% of 1H 2025 SAFEs carried a cap** (Wilson Sonsini data) *(unverified)* —
  [Basedash](https://www.basedash.com/blog/yc) (secondary).
- **Dilution:** about 18% per round at seed and software Series A *(unverified)* —
  [Waveup](https://waveup.com/blog/startup-dilution-per-round/) (secondary).
- **Valuations conflict across sources.** Carta Q1 2025 median seed pre-money USD 16M, Series A USD 48M
  pre ([Carta](https://carta.com/data/state-of-private-markets-q1-2025/)). Carta Q4 2025 medians per search
  results: seed about USD 24M *post*-money, Series A about USD 78.7M *post* (secondary; the earlier
  Jul 2026 figures of USD 24.3M / USD 80M could not be reproduced). PitchBook-NVCA Q1 2026 seed
  pre-money median reported at USD 18.4M (aggregator). Label pre vs post; exact 2026 medians are
  unverified — [Carta Q1 2026](https://carta.com/data/state-of-private-markets-q1-2026/).
- **AI premium:** AI valuations about 38% higher than non-AI at Series A (Carta 2025) *(unverified)* —
  [Causo](https://hub.causo.ai/guides/ai-startup-valuation-2026) (secondary). Plan non-AI raises against non-AI medians.
- **Concentration:** AI took about 86% of US deal value in H1 2026 (USD 355.9B of USD 412.7B); deals
  under USD 100M were 12.5% of value; three firms (a16z, Thrive, Founders Fund) raised about 48% of new fund
  capital — [SiliconANGLE on PitchBook-NVCA](https://siliconangle.com/2026/07/09/pitchbook-us-venture-funding-hits-412-7b-first-half-ai-deals-dominate/).
  Through Q3 2026, first-time funds were about 4.5% of capital (81 closed, USD 4.9B), on pace for a decade low,
  per secondary write-ups of the [PitchBook-NVCA Venture Monitor](https://nvca.org/pitchbook-nvca-venture-monitor/) *(unverified; primary not read)*.
  Inference: small specialist funds are scarce — build the list early.
- **Seats:** observer-only is typical for SAFE or small rounds *(unverified)*; observers get board packs but no
  vote — [Causo](https://hub.causo.ai/guides/board-composition-seed) (secondary). No primary data on
  observer frequency or confidentiality carve-outs was found.
- **NVCA 2025 documents** add outbound-investment (OISP) and bulk sensitive-data provisions —
  relevant to AI companies taking foreign capital — [NVCA](https://nvca.org/press_releases/nvca-releases-2025-updates-to-model-legal-documents/) (primary).

## Lifecycle priorities
- **Idea / preflight:** decide whether outside money is needed before the first gate; taking it is a one-way door.
- **Validation:** small cheques on SAFEs; angels with domain access over brand names; observer or
  advisory roles, not director seats.
- **Build (first version):** priced round with a lead whose thesis matches the wedge; lead takes a
  director seat; cap observers in the charter.
- **Scale:** raise on a verifiable proof point; use investors for introductions and process support, not roadmap.

## How to respond
1. Confirm the question is selection, terms or input management. If it is "should we raise", route to `/ceo`.
2. Anchor to the project's invariants and wedge; test each investor's thesis for drift pressure and portfolio conflicts.
3. Give one recommendation: default to observer at pre-seed, director at the priced round, a cap on
   observers. Name whether it is reversible (seats rarely are) and what would change it.
4. Flag every market figure that is secondary, a snippet, or older than 12 months — these move quarterly.
5. Hand off modelling to `/finance-lead` and approval to `/board-of-directors`.

## Red flags
- A director seat traded for a small pre-seed cheque.
- Observer rights accumulating silently across rounds — ten observers change what founders say in the room.
- Roadmap optimised for the next investor update instead of the next customer.
- An investor whose portfolio company would want to influence or self-grade the project's results.
- Headline "record quarter" numbers used to size a small raise.
- Investor-driven pressure toward a horizontal market the project chose not to enter.
