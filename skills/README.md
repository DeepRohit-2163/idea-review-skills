# Decision skills

26 skills: 23 **decision lenses** (one per startup role, with decision rights),
plus three **method** skills. They are project-agnostic. Each one reads the active project named in
`CLAUDE.md` (if there is one), then `projects/<slug>/context.md`, then `projects/<slug>/role-notes/<role>.md` if
it exists. With no active project, lenses answer generically and point to `/preflight`.

## Standalone use

- **Install:** copy the skill folders (for example `idea-review/`, `preflight/`, `research/` and
  any lenses you want) into `~/.claude/skills/`, or into a project's `.claude/skills/`. Nothing else is required.
- **Project-context files are optional.** `CLAUDE.md`, `projects/<slug>/context.md`,
  `role-notes/`, `docs/index.html` and `docs/_templates/` are used when they exist. When they do not,
  the method skills create what they need in the current directory (`projects/<slug>/`, `research_notes/`,
  `reports/`) and build standalone HTML from the structure described in their `references/` files.
- **Standards are dated 2026-11.** Each "Current standards" section should be refreshed with
  `/research` about every six months, or sooner when a source contradicts it.
- **The standards are a research snapshot, not an authority.** Claims tagged `(unverified)` or
  `(secondary)` were not confirmed against a primary source. Nothing here is legal, financial or tax advice.
- The idea review panel reads the other lens skills; if only the three method skills are installed,
  the panel applies each role from its general job description and says so.

## Method skills — use before deciding

| Skill | Use it for |
|---|---|
| `/idea-review <idea>` | **The entry point for every idea** (mandatory where a `CLAUDE.md` says so; recommended for every new idea). Plays the idea back, runs preflight, convenes all 23 lenses in parallel, stress-tests with scenarios and a pre-mortem, synthesises pros/cons and a verdict, then gets the user's confirmation before anything proceeds. Writes `projects/<slug>/docs/01-idea-review.html` (created in the current directory if the project folder does not exist). |
| `/preflight <idea>` | Any new idea, before committing time or money. Covers constraints across 10 categories, the outside view, riskiest assumptions, a pre-mortem, one-way vs two-way doors and kill criteria. Writes `projects/<slug>/docs/00-preflight.html`. |
| `/research <question>` | Any factual question. Sourced and dated, with verified, secondary and assumed claims kept apart. Delegates breadth to deep research. |

## Decision lenses

| Orbit    | Skills |
|----------|--------|
| Decide   | `/ceo` `/cto` `/cpo` `/coo` `/finance-lead` `/commercial-lead` |
| Build    | `/product-manager` `/engineering-lead` `/product-designer` `/ai-lead` `/qa` `/devops-platform` `/data-analytics` `/security-lead` `/technical-writer-dx` `/customer-success` |
| Counsel  | `/board-of-directors` `/advisory-board` `/fractional-executive` `/investors-observers` |
| Validate | `/subject-matter-expert` `/design-partner` `/legal-regulatory-compliance` |

Rule that every lens enforces: **exactly one Accountable per decision.** If a question lands
outside the invoked role's decision rights, the lens says so and names the role that owns it.

Each lens has the same sections, in this order:
1. Load context
2. Decision rights
3. **Constraints this role must surface before a project starts** (feeds `/preflight`)
4. **Current standards (as of 2026-11)**, sourced and dated
5. Lifecycle priorities
6. How to respond
7. Red flags

## Keeping standards current

The "Current standards" sections were refreshed in 2026-11 (verified against sources on 2026-11-09;
claims marked unverified were not confirmed). Every item carries its source URL inline.
Items marked *(secondary)* or *(unverified)* were not confirmed against a primary source and must
be checked before anything relies on them externally. Refresh with `/research` about every six
months, or sooner when a source contradicts a lens. Update the as-of date when you do.

## Authoring rules

- **Never write `$` followed by a digit.** The Skill tool performs positional argument
  substitution (dollar-sign-plus-number placeholders) on the skill body before the model sees it. A dollar figure
  is silently rewritten using words from the invocation arguments, so a range such as
  USD 8–30k written with dollar signs can arrive as `all–30k`. The file on disk looks correct, which is what makes this hard to
  notice. Write `USD 40k`. Check by searching the skills folder for a dollar sign followed by a digit
  (for example with `grep -rnE` and a pattern of an escaped dollar sign plus `[0-9]`).
- Frontmatter: `name` (matches directory), `description` (third person, what + "Use when…" +
  boundary with adjacent lenses, ≤ 1,024 chars), `argument-hint`. Nothing else, so the skills stay
  portable to the Agent Skills open standard.
- Keep SKILL.md under ~150 lines, with the critical rules near the top. After compaction only the
  first ~5k tokens of an invoked skill survive.
- No `context: fork` on lenses. A forked skill loses the conversation it is meant to judge.
- Project specifics belong in `projects/<slug>/` (or another project folder), never in a lens.
