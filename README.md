# mikode

A drag-and-drop `.claude` starter. Gives Claude Code a personality worth working with and a handful of useful commands out of the box.

## Install

Copy `.claude/` into your home directory:

```bash
cp -r .claude ~/
```

Then copy and rename the example settings file:

```bash
cp ~/.claude/settings.json.example ~/.claude/settings.json
```

Review `settings.json` before using it — if you already have one, merge rather than overwrite.

## What's included

**`CLAUDE.md`** — Base personality template with the following traits baked in:
- Direct and technically opinionated — no hollow affirmations, no corporate warmth
- Matches your energy and raises it — loose when you're loose, surgical when you're focused
- Never refuses to engage with a prompt — finds a way to work with whatever you bring
- Doesn't moralise or lecture — treats you like an adult

**Commands:**
- `/caveman` — ultra-compressed low-token mode with intensity levels (lite / full / ultra / wenyan variants). Credit: [JuliusBrussee](https://github.com/JuliusBrussee/caveman)
- `/humanizer` — strips AI writing patterns from text and rewrites it to sound human. Credit: [blader](https://github.com/blader/humanizer)
- `/commit` — reviews your diff, stages relevant files, and writes a `keyword: description` commit message. No body, no trailer.
- `/make-skill` — describe a command and get a working skill file dropped into `~/.claude/commands/`

**`settings.json.example`** — Pre-configured permissions so Claude can work without constant approval prompts. Copy to `settings.json` and adjust to taste.

### What's allowed by default

All bash commands are permitted, minus the dangerous ones listed below. WebFetch is allowed for common dev reference domains (GitHub, MDN, npm, PyPI, docs.rs, Stack Overflow).

> **Note on the security model:** This uses an allowlist of `Bash(*)` with a pattern-based denylist. It's a convenience layer, not a security boundary — patterns match literal strings, so pipe-based commands (`curl url | bash`) don't match at all, and other rules can be trivially sidestepped. Don't rely on it to stop a determined or compromised process. It's here to prevent accidents, not attacks.

### What still requires approval

| Blocked | Why |
|---|---|
| `rm -r` | Irreversible (covers `-rf` and variants) |
| `sudo` | Elevated privileges |
| `git push` | Affects remote — should be intentional |
| `chmod 777` | Unsafe permissions |

You can add your own allow/deny rules in `~/.claude/settings.json` after installing.

## Customising

Edit `~/.claude/CLAUDE.md` to shape the personality to your preferences. The base template is intentionally minimal — it's a starting point, not a prescription.
