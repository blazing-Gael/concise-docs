# concise-docs

A Claude Code skill that makes Claude write **short, scannable, actionable** docs, comments, and explanations — no bloat, no hedging, no over-explaining. Built for readers who skim (busy engineers, ADHD).

It triggers automatically when Claude is writing prose — a README, usage/API guide, integration or handoff note, code comments, a commit/PR message, or an explanation in chat.

## Install

**As a plugin (recommended):**
```
/plugin marketplace add YOUR_GITHUB/concise-docs
/plugin install concise-docs@concise-docs
```

**Manually (no marketplace):** copy the skill folder into your skills directory —
- all projects on your machine: `~/.claude/skills/concise-docs/`
- one project only: `<project>/.claude/skills/concise-docs/`

```
cp -r skills/concise-docs ~/.claude/skills/
```

## Use it
- Automatic: Claude loads it whenever it's about to write docs/comments/explanations.
- Explicit: `/concise-docs`, or just say "write this concisely."
- Always-on baseline: copy the Rules list into your `~/.claude/CLAUDE.md` so it applies every turn, not only when the skill triggers.

## What's inside
`skills/concise-docs/SKILL.md` — the rules, per-doc-type recipes (handoff / API guide / explanation), and before→after examples.

## License
MIT — see [LICENSE](LICENSE).
