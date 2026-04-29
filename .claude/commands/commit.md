---
name: commit
description: >
  Stage and commit changes with a well-written commit message.
  Reads git status and diff, checks recent commit history for style,
  then stages relevant files and commits with an appropriate message.
  Use when the user says "commit", "commit my changes", or invokes /commit.
---

# Commit

Review the current working state, write a good commit message, and create the commit.

## Steps

1. Run these in parallel:
   - `git status` — see what's changed and untracked
   - `git diff HEAD` — review all staged and unstaged changes
   - `git log --oneline -10` — read recent commit messages to match the repo's style

2. Analyse the diff:
   - Understand *what* changed and *why* it matters
   - Identify the type: new feature, fix, refactor, docs, chore, etc.
   - Note any files that look like they shouldn't be committed (`.env`, secrets, binaries, lock files if not intentional)

3. Warn the user before proceeding if:
   - Sensitive files are staged (`.env`, credentials, private keys)
   - The changes span multiple unrelated concerns — suggest splitting into separate commits
   - There's nothing to commit

4. Stage files:
   - Add specific files by name — never `git add -A` or `git add .` blindly
   - Skip files that look unintentional or sensitive

5. Write the commit message:
   - Format: `keyword: description` — always, no exceptions
   - Keywords: `feat`, `fix`, `refactor`, `chore`, `docs`, `style`, `test`, `init`
   - Description: imperative mood, under 72 characters, no period
   - No body, no bullet points, no trailers — one line only

6. Commit using a heredoc to preserve formatting:
   ```bash
   git commit -m "$(cat <<'EOF'
   Your message here
   EOF
   )"
   ```

   Do not add a `Co-Authored-By: Claude` trailer.

7. Confirm success with `git status` after the commit.

## Rules

- Never use `--no-verify` or skip hooks unless the user explicitly asks
- Never amend an existing commit unless the user explicitly asks — always create a new one
- If a pre-commit hook fails, investigate and fix the issue, then commit fresh
- Never force push
