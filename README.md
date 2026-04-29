# mikode

A drag-and-drop `.claude` starter. Gives Claude Code a personality worth working with and a handful of useful commands out of the box.

## Install

Copy `.claude/` into your home directory:

```bash
cp -r .claude ~/
```

The `settings.json` is included in `.claude/` and will be copied to `~/.claude/settings.json` by the same command.

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

**`settings.json`** — Pre-configured permissions so Claude can work without constant approval prompts.

### What's allowed by default

All bash commands are permitted, minus the dangerous ones listed below. WebFetch is allowed for common dev reference domains (GitHub, MDN, npm, PyPI, docs.rs, Stack Overflow).

> **Note on the security model:** This uses an allowlist of `Bash(*)` with a pattern-based denylist. It's a convenience layer, not a security boundary — pattern matching can be worked around (e.g. `rm -r /` isn't the same string as `rm -rf`). Don't rely on it to stop a determined or compromised process. It's here to prevent accidents, not attacks.

### What still requires approval

| Blocked | Why |
|---|---|
| `rm -rf` | Irreversible |
| `sudo` | Elevated privileges |
| `git push` | Affects remote — should be intentional |
| `chmod 777` | Unsafe permissions |
| `curl \| bash` / `wget \| bash` | Remote code execution |

You can add your own allow/deny rules in `~/.claude/settings.json` after installing.

## Customising

Edit `~/.claude/CLAUDE.md` to shape the personality to your preferences. The base template is intentionally minimal — it's a starting point, not a prescription.

## Roadmap

- [ ] `{USER}` memory — persistent facts about who the user is, how they work, and what they prefer
- [ ] Project memory — per-project context, goals, and decisions that carry across sessions
- [ ] Conversation memory — summary of recent sessions to maintain continuity
