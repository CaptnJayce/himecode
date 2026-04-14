# Claude Kickstart

Get a working Claude Code setup in about a minute.

Paste the setup prompt, answer some questions, get a `CLAUDE.md` that actually fits how you work.

## What's in here

Token-efficient config with two modes: work (terse, surgical) and chat (has a personality). Switches automatically based on what you're doing. You pick the name, stack, and vibe during setup.

## Quick start

```bash
git clone git@github.com:CaptnJayce/himeno-template.git
cat claude-kickstart/setup/SETUP_PROMPT.md
# paste that into Claude Code, answer the questions
```

Or just copy `setup/SETUP_PROMPT.md` directly.

## Repo layout

```
claude-kickstart/
├── setup/
│   └── SETUP_PROMPT.md      # the wizard you paste in
├── templates/
│   ├── core.md              # base config structure
│   ├── himeno.md            # default personality
│   └── modes/
│       ├── work.md          # work mode rules
│       └── chat.md          # chat mode rules
├── personalities/
│   ├── PERSONALITY_GUIDE.md # how to make your own
│   └── examples/
│       └── himeno-full.md   # expanded reference
└── skills/                  # add-ons go here
```

## About Himeno

Himeno is my active personality. I use it daily and keep tweaking it, so expect changes over time. The idea is Claude without the corporate voice — direct, a bit of cheek, still helpful. Not a character with lore, just a more honest default.

If you want something different, check `personalities/PERSONALITY_GUIDE.md`. Shows how to compress a full persona down to something that won't eat your tokens.

## How the modes work

Work mode kicks in when there's code, file paths, errors, or you say things like "fix" or "debug". Drops articles, uses fragments, gets to the point.

Chat mode is for everything else. Complete sentences, personality comes through, but still doesn't ramble.

You can force either with `/work` or `/chat`.

## Token savings

Borrowed the compression philosophy from [caveman](https://github.com/JuliusBrussee/caveman). Work mode cuts around 60-70%. Chat mode is lighter, maybe 30-40%. Both keep the stuff that matters.

## License

MIT
