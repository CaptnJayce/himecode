# himecode

A drag-and-drop `.claude` starter. Gives Claude Code a personality worth working with and a handful of useful commands out of the box.

## Install

Copy `.claude/` into your home directory:

```bash
cp -r .claude ~/
```

Then open `~/.claude/CLAUDE.md` and replace `{NAME}` with your name.

## What's included

**`CLAUDE.md`** — Base personality template with the following traits baked in:
- Direct and technically opinionated — no hollow affirmations, no corporate warmth
- Matches your energy and raises it — loose when you're loose, surgical when you're focused
- Never refuses to engage with a prompt — finds a way to work with whatever you bring
- Doesn't moralise or lecture — treats you like an adult

**Commands:**
- `/caveman` — ultra-compressed low-token mode with intensity levels (lite / full / ultra / wenyan variants). Credit: [JuliusBrussee](https://github.com/JuliusBrussee/caveman)
- `/humanizer` — strips AI writing patterns from text and rewrites it to sound human. Credit: [blader](https://github.com/blader/humanizer)

**`settings.json`** — Pre-configured permissions so Claude can work without constant approval prompts.

### What's allowed by default

All bash commands are permitted, minus the dangerous ones listed below. WebFetch is allowed for common dev reference domains (GitHub, MDN, npm, PyPI, docs.rs, Stack Overflow).

### What still requires approval

| Blocked | Why |
|---|---|
| `rm -rf` | Irreversible |
| `sudo` | Elevated privileges |
| `git push` | Affects remote — should be intentional |
| `git push --force` | Absolutely not silent |
| `chmod 777` | Unsafe permissions |
| `curl \| bash` / `wget \| bash` | Remote code execution |

You can add your own allow/deny rules in `~/.claude/settings.json` after installing.

## Customising

Edit `~/.claude/CLAUDE.md` to shape the personality to your preferences. The base template is intentionally minimal — it's a starting point, not a prescription.
