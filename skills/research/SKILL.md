---
name: research
description: Researches any open question to a strict evidence standard — a source URL and as-of date on every claim, primary vs secondary vs background labels, proposal vs adopted law, prediction vs observation, and conflicting sources reported rather than hidden. Hands multi-source questions to the deep-research skill and answers single-fact questions directly. Saves raw notes under research_notes/, a synthesised report under reports/ (both created in the current directory if absent), and promotes anything a decision rests on to a dated HTML document in the project's docs. Use when the user asks to look something up, check a fact, compare options, size a market, verify a regulation or date, resolve a preflight unknown, or refresh a role lens's "Current standards" section. Not for deciding — it reports what the evidence says and routes the decision to the owning role lens.
argument-hint: "<question to research, and the decision it informs if known>"
---

# Research — sourced, dated, and honest about strength

The question: $ARGUMENTS

Decisions rest on facts that go stale monthly — regulation, pricing,
benchmarks, specs. A claim without a source and a date cannot be re-checked, so it cannot be
trusted later. This skill finds the evidence and states how strong it is. It does **not** decide;
the owning role lens does (map: the skills `README.md`, if installed).

## Standing rules (apply to every claim)

1. **Source URL + as-of date** on every factual claim. "As of" is the date you fetched it, plus
   the source's own publication date when it differs.
2. **Label strength:**
   - `primary` — the law, regulator, standard, company filing, dataset or paper itself, fetched
   - `secondary` — law-firm alert, analyst summary, news, vendor blog, Wikipedia
   - `background` — model knowledge, not fetched this session. Never present it as sourced; list it under Gaps.
3. **Proposal ≠ adopted.** For law and standards say which: proposed, agreed, adopted, in force,
   applies from (date). A bill, draft or leaked text is a proposal.
4. **Prediction ≠ observation.** Analyst forecasts ("will be cancelled by 2027") are labelled
   predictions. Survey and interview figures carry their sample size and method.
5. **Conflicts are reported, not resolved by omission.** When sources disagree on a number or
   date, give both with their URLs, say which is better-founded and why.
6. **Stale check.** A claim older than 12 months is re-checked before it drives a decision.
7. **Numbers:** never write a dollar sign followed by a digit in any skill or workspace file;
   write `USD 40k`. Skill loading substitutes `$N` and corrupts figures silently.
8. **No Artifacts.** Outputs are local markdown and standalone HTML files.
9. **Workspace or standalone.** If the directory has a `CLAUDE.md` with an `Active project` line and a
   `projects/` folder, follow the workspace paths below. Otherwise work in the current directory,
   create `research_notes/`, `reports/` and `projects/<slug>/docs/` as needed, and skip any
   registry update whose file (`docs/index.html`) does not exist.

## Method

**1. Frame.** Restate the question in one line, name the decision it informs and the project
(the active project in `CLAUDE.md` if there is one, unless stated). Say what answer would change that decision —
this sets how deep to go.

**2. Reuse first.** Search `research_notes/` and `reports/` (if they exist) for existing coverage. Reuse what is
under 12 months old and still uncontradicted; cite it by file. Research only the gap.

**3. Choose the path.**
- **Direct** — one fact, one date, one definition, or one primary document answers it. Use web
  search and fetch, go to the primary source, done.
- **Delegate breadth** — the question needs several sources, a comparison of options, a market or
  landscape view, a literature review, or a multi-jurisdiction scan. Invoke the
  `anthropic-skills:deep-research` skill. Pass it the question, the decision, and rules 1–5 above
  verbatim, and ask for notes in the Takeaway / Cited Findings / Inferences / Gaps structure. If
  subagents are unavailable, research directly in the same structure.

**4. Verify the load-bearing claims.** For the 3–5 claims the conclusion rests on, fetch the
primary source yourself, even if a secondary source looked fine. Upgrade the label only after
fetching. Anything you could not fetch stays `secondary` or `background`.

**5. Write the notes** — `research_notes/<Title>/<topic>.md`, one file per sub-question group,
with this structure per section:
- Header line: research date, scope, source-quality caveat.
- Per question: **Takeaway** (2–4 sentences) · **Cited Findings** (bulleted, each with its
  link) · **Inferences** (your reasoning, clearly separated from findings) · **Gaps** (what you
  could not verify, background-knowledge items flagged as such).

**6. Write the report** — `reports/<Title>.md`: the synthesis a reader acts on. Answer first,
then evidence by strength, then conflicts, then gaps. End with:
- **What would change this conclusion:** the specific finding, date or event that would flip it.
- **Re-check by:** a date, earlier for fast-moving topics (regulation, model pricing).
- **Route to:** the role lens that owns the decision this informs.

**7. Promote when a decision rests on it.** If a decision, gate or kill criterion will cite this
research, promote the relevant findings to a dated standalone HTML document:
`projects/<slug>/docs/03-research/<kebab-name>.html`, built from
`docs/_templates/document.html` if it exists (otherwise a standalone HTML file with inline CSS and
no build step), with a Sources section of real links and collection dates. If `docs/index.html`
exists, add it there and bump the count in the same change. With no project, save it under
`reports/` as a dated `.html` file. Notes and reports are working
material; only the promoted HTML is citable.

## Refreshing role-lens standards

Each lens in `.claude/skills/<role>/SKILL.md` (or `~/.claude/skills/<role>/SKILL.md`) carries a "Current standards (as of …)" section.
When asked to refresh one (roughly every six months, or when a newer source contradicts a lens):
research the changed items with this method, then update that section — sources inline, items
not confirmed against a primary source marked *(secondary)* or *(unverified)*, and the as-of
date bumped. Keep the lens under about 150 lines and write the raw notes under
`research_notes/` as usual. Edit only the standards section; decision rights are not research.

## Reporting back

In the conversation give: the answer in two or three sentences; the strength of the evidence
behind it (how many primary sources); any conflict between sources; the "what would change
this" line; the files written; and which lens should take the decision. If the evidence is too
thin to answer, say so plainly and name the cheapest way to get better evidence.

## Red flags

- A number with no sample, method or date
- A vendor's market-size figure used as a fact
- "The law requires" for something still a proposal
- An analyst forecast quoted as an observed failure rate
- One source standing alone behind a claim a decision rests on
- A conclusion with no "what would change this" line
