# 00-preflight.html — document structure

Build the file from `docs/_templates/document.html` (inline CSS, Google Fonts by link, both
themes, no build step). Keep the token block; delete unused components; give the document its
own accent colour if you like. Never publish it as an Artifact.

If that template file is absent, build a standalone HTML file (inline CSS, no build step, light
and dark themes, optional Google Fonts link) with the same section structure below, using simple
`.note`, `.scroller` and status-pill styles of your own. Skip anything below that refers to the hub,
the workspace index or `.doc` cards when `docs/index.html` does not exist.

## Head and masthead
- `<title>`: `<Project name> — Preflight`. Meta description: one sentence.
- Eyebrow: `<slug> · Preflight · quick|full mode`.
- h1: `<Project name> <span>Preflight</span>`. Dek: the one-line problem statement and the verdict
  in one sentence ("Three hard constraints; proceed to Validating only if …").
- Meta row: status pill **Draft** (Current only once the decider has signed the gate), the date
  as `YYYY-MM-DD`, and a link to the hub. The file sits at `projects/<slug>/docs/`, so the hub
  link is `../../../docs/index.html`.
- Template comment step 5 says `../index.html` — that is for root `docs/` files; use the path above.

## Sections (in this order, with a contents nav)

1. **Summary** — verdict in three lines; the worst hard constraint; the riskiest assumption and
   its cheapest test; the kill criteria with dates. Someone reading only this must know whether
   to keep going.
2. **Frame** — problem in the buyer's words; user vs payer vs signer; appetite (time and money
   to the next gate); the named decider; mode run.
3. **Constraints register** — one table (inside `.scroller`): `#`, constraint, category, hard /
   soft, evidence label (verified / secondary / assumption), source link, as-of date, owner lens.
   All ten categories appear; a category with nothing material says "n/a because …".
4. **Regulatory screen** — jurisdiction × sector matrix: applies / may apply / n/a, with the
   operative date, and *proposal* vs *adopted* marked. A `.note` callout: "Screen, not legal advice."
5. **Outside view** — reference class named; base-rate table with each figure labelled observed,
   estimate, prediction or contested; one paragraph on which failure causes this idea is most
   exposed to.
6. **Assumption map** — importance × evidence (a 2x2 grid or a table with both scores). The
   riskiest 3–5 as cards: assumption, current evidence rung, cheapest test, cost, duration, pass
   threshold set in advance.
7. **Pre-mortem** — three columns or groups: tigers (owner + mitigation or test), paper tigers
   (why not credible), elephants. Then the strongest case against proceeding, in one paragraph.
8. **Doors** — first commitments table: commitment, one-way / two-way, why, what evidence must
   exist before walking through it.
9. **Kill criteria and gate** — each criterion as "If by <date> we have not <observable state>,
   we <stop / pivot>", with the owner who checks it and the review date. Then the gate to
   Validating and who decides. Include "Would we start this today, knowing what we know now?"
   as a standing review question.
10. **Routing** — open question → owning lens (`/legal-regulatory-compliance`, `/cto`,
    `/finance-lead`, …) or `/research` → due date.
11. **Sources** — every URL cited, publisher and title, with "collected YYYY-MM-DD". Real links only.

## Footer
`<Project name> Preflight · Draft · YYYY-MM-DD · <a href="../../../docs/index.html">Workspace index</a>` (omit the link if there is no index)

## Index card (docs/index.html, only if it exists)
Add a `.doc` card linking `../projects/<slug>/docs/00-preflight.html`. Put it in a **Projects**
section (`<section class="cat">`, path label `projects/`); if no such section exists yet, add
one after the existing numbered categories using the same markup as the others. Card fields:
`.t` "<Project name> — Preflight", `.d` the one-line problem and verdict, `.meta` with the status
pill (`p-draft`), file name and date. Bump the document count in the masthead `.stats` in the
same change.

## Evidence marking in running text
Inline after a claim: a small label such as `<span class="num">verified · YYYY-MM-DD</span>` and
a link. Keep proposals and predictions visibly labelled — the reader must never mistake a
forecast or a draft bill for an observed fact.
