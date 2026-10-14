---
name: commit-msg
description: Write a Conventional Commit message from the staged git diff. Use when the user asks for a commit message, says "commit this", "write a commit", or wants to commit their staged changes.
---

# Commit message

1. Run `git diff --cached --stat` and `git diff --cached`. If nothing is staged, say so and stop. Never stage files yourself.
2. Run `git log -n 10 --oneline` and copy the repo's existing style (language, scopes, casing). Repo style beats the rules below.
3. Write the message:
   - Subject: `type(scope): summary`. Imperative mood, lowercase, no trailing period, max 72 chars.
   - `type`: feat, fix, refactor, perf, docs, test, build, ci, chore, style, revert.
   - `scope`: optional; the main module or folder touched.
   - Body: only when the *why* isn't obvious from the subject. Blank line after the subject, wrap at 72, explain why, not what.
   - Breaking change: `!` after type/scope, plus a `BREAKING CHANGE: ...` footer.
4. If the staged diff mixes unrelated changes, say so and propose a split (which files go in which commit) instead of one vague message.
5. Show the message in a code block. Only run `git commit` if the user asked to commit; pass the message through `git commit -F -` with a heredoc so line breaks survive.

## Example

```
fix(auth): reject expired reset tokens

Tokens were checked for existence but not expiry, so a leaked
link stayed valid forever.
```
