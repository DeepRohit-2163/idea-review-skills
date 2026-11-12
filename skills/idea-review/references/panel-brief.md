# Panel brief: give this to each panel agent verbatim, with the blanks filled

You are one group of an idea-review panel for the project below.

- **Idea (as played back and confirmed by the user):** <playback>
- **Project slug:** <slug>
- **Your lenses:** <list>

## Do this

1. Read `CLAUDE.md` (if present), `projects/<slug>/context.md` and `projects/<slug>/docs/00-preflight.html`
   (the constraint scan, base rates and assumptions are already there, so build on them rather than redoing them).
2. For **each** of your lenses, read `.claude/skills/<lens>/SKILL.md` (or `~/.claude/skills/<lens>/SKILL.md`) in full and apply it as
   that role. If that skill is not installed, apply the role from its general job description and
   write "lens not installed" in its block. Use its decision rights, its "constraints to surface" questions, its dated "Current
   standards", and its red flags. Stay inside the lens's rights. Anything outside them is routed
   to the owning role, not answered.
3. Research only what a verdict hinges on and cannot be answered from the lens or preflight.
   Cite the URL and as-of date, and keep this to a few searches per lens.

## Output contract, one block per lens

```
### /<lens> — verdict: Go | Go with conditions | Park | Kill | n/a
Confidence: low | medium | high — because <one line>
Pros (from this role's view):    - … [evidence label]
Cons / risks:                    - … [evidence label] (severity: high/med/low)
Hard constraints found:          - … (what it forces)
Scenarios this role fears most:  - …
What would change my verdict:    - <observable evidence>
Cheapest next test:              - <test, cost, duration, pass threshold>
Routed to other roles:           - <question> → /<owner>
```

Rules:
- Every lens gets a block. "n/a" must say why in one line.
- Cons are as specific as pros. Never write "competition" or "execution risk" without the specific competitor or failure mode.
- Label evidence `verified`, `secondary` or `assumption`.
- Never write a dollar sign followed by a digit; write `USD 40k`.

Write all blocks to `projects/<slug>/review/panel-<group>.md`. Return a summary of 15 lines or
fewer: the verdict per lens, the three most severe cons across your group, and any hard
constraint not already in the preflight.
