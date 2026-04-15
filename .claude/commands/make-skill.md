---
name: make-skill
description: >
  Scaffold a new slash command (skill) and save it to ~/.claude/commands/.
  Interviews the user about what they want, drafts the skill file, and writes it locally.
  Use when the user says "make a skill", "create a command", "new slash command", or invokes /make-skill.
---

# Make Skill

Help the user create a new custom slash command and save it to `~/.claude/commands/`.

## Steps

1. **Understand the intent.**
   If the user invoked `/make-skill` with no arguments, ask:
   - What should this command do?
   - What should trigger it — a specific phrase, a workflow, a type of task?
   - Any edge cases or constraints to handle?

   If they've described it already (e.g. `/make-skill a command that summarises my PR`), skip straight to drafting.

2. **Pick a name.**
   Short, lowercase, hyphen-separated. Should read naturally after a `/` (e.g. `pr-summary`, `changelog`, `debug-log`).

3. **Draft the skill file.**

   Use this structure:

   ```markdown
   ---
   name: <name>
   description: >
     One to three sentences. What it does, when it triggers,
     and any key behaviours worth calling out.
   ---

   # <Title>

   <What this skill does and why — one short paragraph.>

   ## Steps

   1. ...
   2. ...

   ## Rules

   - ...
   ```

   Guidelines:
   - Instructions should be imperative and explain the *why*, not just the *what*
   - Keep it under 300 lines — if it's getting long, the skill is probably doing too much
   - Be specific about edge cases that need handling
   - Don't add steps for things Claude will do naturally

4. **Show the draft** and ask if it looks right before writing it.

5. **Write the file** to `~/.claude/commands/<name>.md`.

6. **Confirm** — tell the user the skill is ready and how to invoke it (`/<name>`).

## Rules

- Don't write the file until the user has seen the draft and approved it (or explicitly said to just write it)
- If the skill is very similar to an existing command in `~/.claude/commands/`, mention it — maybe they want to extend rather than duplicate
- Skills are markdown files, not code — keep them readable as documentation
