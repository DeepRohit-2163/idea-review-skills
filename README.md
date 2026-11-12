# Idea Review Skills

26 agent skills, built and tested in [Claude Code](https://claude.com/claude-code), that review any project idea before you build it: a preflight constraint scan, 23 role lenses (CEO to QA), and an orchestrator, `/idea-review`, that runs them all in parallel and stops for your explicit confirmation before anything proceeds.

Site: https://deeprohit-2163.github.io/idea-review-skills/

## Install

**Option A, from your terminal** (works the same on Windows, macOS and Linux):

```
claude plugin marketplace add DeepRohit-2163/idea-review-skills
claude plugin install idea-review@idea-review-skills
```

**Option B, inside a Claude Code session:** type `/plugin marketplace add DeepRohit-2163/idea-review-skills`, then `/plugin install idea-review@idea-review-skills`. If you use the `/plugin` menu instead, enter only `DeepRohit-2163/idea-review-skills` in the source field, with no `https://` page URL, no `@...` suffix and no leading slash.

Then **start a new Claude Code session** (new skills load at session start) and run, for example, `/idea-review:idea-review a marketplace for used climbing gear`. Run it from an empty or scratch folder: the review creates `projects/` and `research_notes/` in the current directory.

Needs a recent Claude Code with plugin support (tested on 2.1.308) and `git` on your PATH. If your organisation manages Claude Code settings, it may block third-party marketplaces; ask your admin or use the copy method below.

Plugin skills are namespaced, so each skill is `/idea-review:<skill>` (for example `/idea-review:ceo`, `/idea-review:preflight`). Inside the skill text the lenses are written as `/ceo`; read that as the namespaced command.

**Prefer bare `/idea-review`, `/ceo` and so on?** Copy the folders instead:

```
git clone https://github.com/DeepRohit-2163/idea-review-skills.git
cp -r idea-review-skills/skills/* ~/.claude/skills/
```

Project-context files (`CLAUDE.md`, `projects/`) are optional. The method skills create what they need in the current folder. See [skills/README.md](skills/README.md) for the full skill list and decision rights.

## Other coding agents (Codex and similar)

The skills are plain Markdown instruction files (`skills/<name>/SKILL.md`), so the content is not tied to one tool. Only the install route is Claude Code specific:

- **Claude Code:** the `/plugin` install above, or copy to `~/.claude/skills/`. This is the only setup tested.
- **Agents that read `SKILL.md`-style skill folders** (check your tool's docs for its skills folder): copy the folders from `skills/` there.
- **Any other agent:** paste a skill's body into the prompt or reference it from your `AGENTS.md`, for example "follow `skills/cto/SKILL.md` for architecture decisions".
- **Differences to expect:** the `/name` command names, the frontmatter handling and the parallel panel in `/idea-review` (which assumes the agent can run sub-agents in parallel) are Claude Code behaviour. Elsewhere, run the lenses one at a time. Plugin-style `/idea-review:<skill>` names do not exist outside Claude Code.

Reports of what works in other agents are welcome as issues.

## How current is it?

Each lens has a dated "Current standards" section, checked against live sources on 2026-11-09. Claims are tagged primary, secondary or `(unverified)`. These sections are a research snapshot, not an authority; refresh them with `/research` about every six months. Nothing here is legal, financial or tax advice.

## Licence

[MIT](LICENSE)
