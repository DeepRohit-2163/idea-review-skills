---
name: idea-review
description: Full multi-role review of any project idea, product concept, venture, feature bet or "should I do X" question. Restates the idea and confirms it, runs the preflight constraint scan, convenes all 23 role lenses in parallel (each gives pros, cons, hard constraints and a verdict), stress-tests the idea with scenarios and a pre-mortem, synthesises one pros/cons ledger and recommendation, then plays everything back for the user to confirm before any work proceeds. Use whenever the user brings a new idea, project, business, product or opportunity, even when phrased casually ("what do you think of…", "I want to build…"). Not for a single narrow decision inside an approved project; use that role's lens.
argument-hint: "<the idea, in your own words>"
---

# Idea review — every lens, every scenario, confirmed understanding

The idea: $ARGUMENTS

The point of this review is that nothing about an idea surprises the user later. Every role
looks at it, every plausible future is tested against it, and the user confirms they understand
the pros, cons and constraints **before** any time, money or code is committed. A review that
skips a lens, hides a con, or proceeds without the user's confirmation has failed at its job.

## Non-negotiables

- **All 23 lenses report.** A lens with little to say still writes one line: "n/a because …".
  A silent lens is indistinguishable from a forgotten one.
- **Cons get equal weight to pros.** Lead with whatever would kill the idea, not with enthusiasm.
- **Evidence labels on every claim:** `verified` (primary source, URL, as-of date), `secondary`
  (URL), or `assumption` (needs a test). Predictions ≠ observed rates; proposals ≠ law.
- **One Accountable per decision.** Lenses advise; the recommendation is made by the `/ceo` lens
  (or the decider named in step 1), and the final call belongs to the user.
- **Stop at the confirmation gate (step 7).** No build, purchase, signup or outreach until the user confirms.
- Never write a dollar sign followed by a digit (write `USD 40k`). Never publish an Artifact; output is a local standalone HTML file.
- **Workspace or standalone.** A *workspace* is a directory with a `CLAUDE.md` containing an `Active project` line and a `projects/` folder. If it exists, follow the workspace paths below. If not, work in the current directory and create `projects/<slug>/` as needed; skip any step that updates a file that does not exist (`docs/index.html`, `projects/README.md`, `CLAUDE.md`).

## Method, in order

**1. Intake and playback.** Restate the idea in five lines: problem (in the buyer's words), who has
it, who pays, what we'd make, and the appetite (time and money before the next gate). List the
assumptions you made in order to fill gaps. If something material is unknowable from the prompt,
such as target customer, geography, budget, solo or team, or side project or full-time, ask up to
4 questions in one `AskUserQuestion` call. Otherwise state the assumptions and continue. Derive a
kebab-case slug. If `CLAUDE.md` has an **Active project** line, set it to the slug; otherwise
note the slug in the review document and `context.md`.

**2. Preflight.** Run the `/preflight` method (full mode by default, quick only if the user asked
for speed). It scaffolds `projects/<slug>/` (created in the current directory if absent) and writes the constraint register, base rates,
assumption map and kill criteria. The panel in step 3 reads its output, so it comes first.

**3. Role panel: all 23 lenses, in parallel.** Spawn five `general-purpose` agents in a single
message, one per group below. Give each the brief in
[references/panel-brief.md](references/panel-brief.md), the idea playback, the slug and its lens
list. Each agent reads its lenses' `SKILL.md` files from `.claude/skills/<lens>/` (or `~/.claude/skills/<lens>/`) and applies
them faithfully. If a lens skill is not installed, the agent applies that role from its general job
description and marks the block "lens not installed". It writes `projects/<slug>/review/panel-<group>.md` and returns a summary.

| Group | Lenses |
|---|---|
| decide | ceo, cpo, cto, coo, finance-lead, commercial-lead |
| product | product-manager, product-designer, technical-writer-dx, customer-success, data-analytics |
| tech | engineering-lead, ai-lead, qa, devops-platform, security-lead |
| counsel | board-of-directors, advisory-board, fractional-executive, investors-observers |
| validate | subject-matter-expert, design-partner, legal-regulatory-compliance |

If agents are unavailable, apply each lens yourself in sequence. The output contract stays the same.

**4. Scenarios.** Using the panel outputs, write [references/scenarios.md](references/scenarios.md):
- **best, base and worst case** with numeric ranges (customers, revenue, cost, months to the
  gate), each anchored to the base rates from preflight
- **at least six stress scenarios** from that file
- the **pre-mortem** from preflight, extended with any new tigers the panel found

For each scenario, state what happens to the idea, the early-warning signal, and the
pre-planned response.

**5. Cross-examination.** Find where lenses disagree (e.g. `/commercial-lead` says enterprise,
`/finance-lead` says the runway can't survive enterprise cycles). For each conflict: both
positions, the evidence on each side, the owning role per the decision rights, and its call.
Unresolvable on current evidence → it becomes a test with a date.

**6. Synthesis.** One deduplicated **pros/cons ledger** (each item: lens(es), evidence label,
severity), the **hard constraints** register, **riskiest assumptions** with the cheapest test
for each, **kill criteria** as state + date, and a recommendation from the `/ceo` lens:
**Go**, **Go with conditions** (list them), **Park** (what would reopen it) or **Kill** (why).
Then write `projects/<slug>/docs/01-idea-review.html` per
[references/review-template.md](references/review-template.md). If the workspace has `docs/index.html`, register it there
(card and count bump); if it has `projects/README.md`, update the row. Update `projects/<slug>/context.md`
(create it if missing). Otherwise skip the registry steps.

**7. Understanding confirmation (the gate).** Present this in chat, concisely, and ask the user to
confirm or correct it with `AskUserQuestion`:
- the idea as understood, in one or two sentences
- the top 5 pros and the top 5 cons, with the single biggest risk first
- the hard constraints and what each one forces
- the one-way doors the user would be walking through
- the recommendation, and its conditions or kill criteria

Ask, at minimum: "Is this the idea?" · "Do you accept these cons and constraints?" · "Proceed as
recommended, proceed differently, or stop?". Record the answers and date in the HTML doc's
**Confirmation** section and in `context.md`. A correction to the idea sends you back to the
earliest step it invalidates.

## When you finish

Report in under 20 lines: the verdict, the top 3 pros and cons, the worst hard constraint, the
riskiest assumption and its test, the kill criteria with dates, the user's confirmation status,
and the files written.

## Red flags

- A lens that returned only pros, or only "n/a", for an idea squarely in its domain
- Scenarios with no numbers, or a worst case that is just "slower growth"
- A recommendation that ignores a hard constraint the panel raised
- Proceeding past step 7 without an explicit user answer
- A pros list longer than the cons list on an idea with no paying customer yet
