# Idea Review Skills

26 [Claude Code](https://claude.com/claude-code) skills that review any project idea before you build it: a preflight constraint scan, 23 role lenses (CEO to QA), and an orchestrator, `/idea-review`, that runs them all in parallel and stops for your explicit confirmation before anything proceeds.

Site: https://deeprohit-2163.github.io/idea-review-skills/

## Install

```
git clone https://github.com/DeepRohit-2163/idea-review-skills.git
cp -r idea-review-skills/skills/* ~/.claude/skills/
```

Then, in Claude Code: `/idea-review a marketplace for used climbing gear`

Project-context files (`CLAUDE.md`, `projects/`) are optional. The method skills create what they need in the current folder. See [skills/README.md](skills/README.md) for the full skill list and decision rights.

## How current is it?

Each lens has a dated "Current standards" section, checked against live sources on 2026-11-09. Claims are tagged primary, secondary or `(unverified)`. These sections are a research snapshot, not an authority; refresh them with `/research` about every six months. Nothing here is legal, financial or tax advice.

## Licence

[MIT](LICENSE)
