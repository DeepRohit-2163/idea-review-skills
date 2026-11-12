---
name: preflight
description: Runs a constraint preflight on a raw idea before any real time or money is committed — problem statement, a ten-category constraint scan (customer, market and timing, technical, data, regulatory, financial, operational, team and founder-personal, ethical, dependencies), base rates, riskiest assumptions with cheapest tests, a pre-mortem, one-way vs two-way door calls and dated kill criteria. Scaffolds a project folder under projects/ (created in the current directory if needed), writes its docs/00-preflight.html and fills its context.md. Normally runs as step 2 of /idea-review, which every new idea goes through. Invoke it directly only when the user explicitly wants a constraint-only pass. Quick mode is a 30-minute checklist pass; full mode resolves unknowns with /research. Not for deciding — it surfaces constraints and routes each one to the owning role lens. Not the entry point for a new idea; use /idea-review.
argument-hint: "[quick|full] <the idea in one or two sentences>"
---

# Preflight — know every constraint before committing

The idea: $ARGUMENTS

Preflight exists because the expensive failures are the ones visible on day one to anyone who
looked: an employment clause, a regulation already in force, a buyer with no budget line. It
**surfaces and routes**; it does not decide go/no-go. That belongs to the decider named in step 1,
using the kill criteria written in step 7 — criteria written after the evidence arrives are
rationalisation.

## Standing rules (apply throughout)

- **Every claim carries a label and an as-of date:** `verified` (primary source fetched, URL),
  `secondary` (law-firm alert, summary, vendor — URL), or `assumption` (background knowledge or
  belief — no URL, needs a test). Proposals are not law; predictions are not observed rates.
- **Opinions are not evidence.** Interview statements cap at weak until someone commits time,
  reputation or money (ladder in [references/checklist.md](references/checklist.md#evidence-ladder)).
- **Outside view before inside view.** Base rates first, then adjust for what is specific.
- **Never write a dollar sign followed by a digit** in any file; write `USD 40k`. Skills and
  some tooling substitute `$N` and corrupt the figure silently.
- **Never publish an Artifact.** Output is a local standalone HTML file that must survive being
  emailed on its own.
- **Workspace or standalone.** A *workspace* is a directory with a `CLAUDE.md` containing an `Active project` line and a `projects/` folder. If it exists, follow the workspace paths below. If not, work in the current directory and create `projects/<slug>/` as needed; skip any step that updates a file that does not exist (`docs/index.html`, `projects/README.md`, `CLAUDE.md`).

## Mode

Read the first word of the arguments. Default to **quick** if absent.

| | Quick (about 30 min) | Full (hours to days) |
|---|---|---|
| Scope | Every checklist question answered or marked unknown | Same, plus unknowns resolved |
| Research | None beyond the base rates and regulatory screen already in the checklist | `/research` on every hard-constraint unknown and each of the top 3 assumptions |
| Evidence | Mostly `assumption`; each unknown gets a named test and owner lens | Hard constraints `verified` or explicitly left `secondary` with a reason |
| Doc status | Draft | Draft until the decider signs the gate, then Current |

Quick mode is enough to decide whether full mode is worth the time. Say which mode ran in the
document masthead.

## Method — in order

**0. Scaffold.** Derive a short kebab-case slug. If `projects/<slug>/` is missing, create it,
copy `projects/_template/context.md` to `projects/<slug>/context.md` (if that template is absent,
create `context.md` with the headings: identity, status, appetite, hard constraints, riskiest
assumptions, kill criteria, gate), and create `projects/<slug>/docs/`. If it exists, read `context.md` first and extend, never overwrite.

**1. Frame.** One sentence each, and ask the user only for what you cannot infer:
- Problem statement in the *buyer's* words — who has what problem, observed how (RAND's most
  common AI-project failure is a misunderstood problem).
- Who pays, from which budget, and who signs. Payer and user often differ.
- **Appetite**: the time and money willing to spend before the next gate (fixed time, variable scope).
- The single decider for go/no-go.

**2. Constraint scan.** Work through all ten categories in
[references/checklist.md](references/checklist.md). For each question record: answer, evidence
label, hard or soft, owner lens. A **hard** constraint kills or reshapes the project; a soft
one costs time or money. Do not skip a category because it "obviously doesn't apply" — write
"n/a because …" so the reader can disagree. The regulatory screen is jurisdiction × sector and
its dates go stale fast; carry the as-of date of every legal claim.

**3. Outside view.** Name the reference class (e.g. "VC-backed B2B SaaS", "enterprise GenAI
pilot", "solo bootstrapped tool"). Quote the base rates in
[references/checklist.md](references/checklist.md#outside-view-base-rates) with their labels —
CB Insights 2026 as observed; RAND as an interview-based estimate; Gartner as a prediction;
MIT NANDA as contested. Then state which failure causes this idea is most exposed to, and why.

**4. Assumption map** (Bland / Strategyzer). List assumptions per risk type (desirability,
feasibility, viability, adaptability). Place each on importance × evidence. The **riskiest 3–5**
are high importance, low evidence. For each: the cheapest test that produces *do*-level evidence,
its cost, its duration, and the result that would count as a pass — set before running it.

**5. Pre-mortem** (Klein). "It is twelve months from now and this has failed. Why?" Generate
reasons first, judge later. Sort them (Doshi): **tigers** (real threats — each gets an owner and
a mitigation or a test), **paper tigers** (feared but not credible — say why), **elephants**
(what nobody is saying — the founder's own commitment, the uncomfortable market fact). Then
one pass arguing the strongest case *against* proceeding.

**6. Doors.** List the first commitments the idea would require. Classify each as **one-way**
(irreversible or costly to undo: resigning, incorporating in a jurisdiction, taking investor
money, signing a lease, a data architecture that stores personal data, telling the employer's
customers) or **two-way** (cheap to reverse). Only one-way doors deserve heavy analysis; delay
them until the evidence that justifies them exists.

**7. Kill criteria and gate.** Write 2–4 kill criteria as **state + date**: "If by
<date> we do not have <observable state>, we stop / pivot." Observable, owned, checked on a
calendar date. Prefer do-level states ("3 buyers signed a paid pilot") over say-level states.
Then the gate: what must be true to move from Preflight to Validating, and who decides. Add
Annie Duke's test to the review: would we start this today, knowing what we know now?

**8. Write and register.** All in the same change:
1. Write `projects/<slug>/docs/00-preflight.html` from `docs/_templates/document.html` if it exists (otherwise a standalone HTML file with inline CSS),
   with the sections in [references/preflight-template.md](references/preflight-template.md).
2. Fill `projects/<slug>/context.md`: identity, status `Preflight — <date>`, appetite, the
   **hard** constraints only in the register, riskiest assumptions, kill criteria, gate.
3. If `projects/README.md` exists, add a row to its table (slug, status, one line, docs path);
   otherwise create it with that table.
4. If `docs/index.html` exists, add a card (see the template reference for placement) and bump the
   document count in its masthead stats; otherwise skip.

## Routing — preflight surfaces, lenses decide

Each category names the lens that owns its follow-up. End the document with a routing table:
open question → owning lens → by when. The most common hand-offs: regulatory, IP and employment
clauses → `/legal-regulatory-compliance`; feasibility, build/buy, data architecture → `/cto`;
runway, unit economics, pricing mechanics → `/finance-lead`; problem definition and discovery →
`/product-manager`; thesis, go/no-go tiebreak → `/ceo`; unknown facts → `/research`.

## When you finish

Report to the user in under 15 lines: mode run, hard constraints found (count and the worst
one), the riskiest assumption and its cheapest test, the kill criteria with dates, and the
files written. If a hard constraint is a likely kill (e.g. an employer IP clause covering the
idea), lead with it — do not bury it in the document.

## Red flags

- A constraint register with no hard constraints — you did not look hard enough
- Kill criteria without a date, or written in say-level terms ("customers like it")
- A market size built top-down from an analyst report rather than accounts × evidenced price
- A regulatory claim without an as-of date, or a proposal treated as law
- Any work on the idea using a current employer's time, devices or data
- Treating a one-way door as reversible because it is early
