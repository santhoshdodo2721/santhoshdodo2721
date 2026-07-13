---
name: git
description: 'Use for Git workflows: status, diff, branch, commit, merge, rebase, stash, cherry-pick, reset, revert, tagging, resolving conflicts, and safe repository troubleshooting.'
argument-hint: 'Git task or workflow'
user-invocable: true
disable-model-invocation: false
---

# Git Skill

## When to Use
- Inspect repository state with `git status`, `git diff`, or `git log`
- Create or switch branches
- Stage, commit, amend, or unstage changes
- Merge, rebase, cherry-pick, revert, or reset safely
- Handle conflict resolution and repository cleanup
- Prepare changes for review or release tagging

## Workflow
1. Check the current state first with `git status` and the relevant diff.
2. Identify the smallest safe change needed before editing history.
3. Prefer reversible operations such as `git stash`, `git revert`, or a new commit over destructive history edits.
4. If history must be rewritten, confirm the target branch and scope before using `git reset`, `git rebase`, or `git push --force-with-lease`.
5. Verify the result with `git status`, `git diff`, and, when relevant, tests or checks.

## Common Guidance
- Use `git branch --show-current` to confirm the active branch before making changes.
- Use `git log --oneline --decorate -n 10` to understand recent history.
- Use `git diff --cached` to review staged changes before committing.
- Use `git restore` for discarding local file changes and `git restore --staged` for unstaging.
- Use `git revert` for shared history; use `git reset` only when rewriting local history is acceptable.
- Use `git fetch` before comparing against remote branches or resolving upstream differences.
- For conflicts, inspect both sides carefully and keep the intent of each change clear.

## Safety Rules
- Do not assume the repository is clean.
- Do not rewrite shared history unless explicitly requested.
- Do not force-push unless the user asked for it or it is clearly required.
- Prefer the least destructive command that solves the problem.

## Output Expectations
- Explain the current branch, changed files, and the effect of any Git command you recommend.
- Call out any risky operation before using it.
- If the request is ambiguous, ask whether the user wants inspection, cleanup, history rewriting, or release preparation.
