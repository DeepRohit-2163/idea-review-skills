# 01-idea-review.html: document structure

Start from `docs/_templates/document.html` and follow `docs/README.md` if the workspace has them.
If that file is absent, build a standalone HTML file (inline CSS, no build step, light and dark
themes, optional Google Fonts link) with the same section structure below. Either way the
document is standalone and carries a status and date in the masthead.
Link it to `00-preflight.html` with relative paths. The hub link is `../../../docs/index.html`
when that file exists; otherwise omit it.

## Masthead
- Eyebrow: `Idea review · <slug>`
- Title: the idea's short name
- Dek: the verdict, in one line
- Status: `Draft` until the user confirms in step 7, then `Current`. Give the date.
- A stat row: verdict · lenses reporting (must be 23/23) · hard constraints · kill criteria

## Sections, in order, with a contents nav
1. **Verdict and the one thing to know**: the recommendation, its conditions, and the single biggest risk.
2. **The idea as understood**: the five-line playback and the assumptions made.
3. **Pros and cons ledger**: two columns of equal visual weight. Each item shows its lens tags, an evidence label and severity.
4. **Hard constraints**: what each one forces, its owner lens, and its evidence.
5. **Role panel**: a table of all 23 lenses (verdict, confidence, top pro, top con), followed by collapsible `<details>` with each lens's full block.
6. **Where the roles disagree**: each conflict, the owning role, and its call or the test that settles it.
7. **Scenarios**: the best/base/worst table, the stress scenarios (likelihood × impact), and the pre-mortem tigers, paper tigers and elephants.
8. **Riskiest assumptions and cheapest tests**: each with a pass threshold set in advance.
9. **One-way doors**: what they are, and what evidence must exist before walking through each.
10. **Kill criteria and gate**: state + date, with an owner.
11. **Confirmation**: the user's answers to the step 7 questions, verbatim, with the date. Write "Pending" until answered.
12. **Sources**: every URL, with its evidence label and as-of date.

## Index card
If `docs/index.html` exists, add a card under the project's entry in the Projects section and bump the
document count. If it does not exist, skip this.
