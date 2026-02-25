---
name: git-commit-review
description: Review staged changes, create clear commit messages, and push to current branch
license: MIT
compatibility: opencode
metadata:
  audience: developers
  workflow: git
---

## What I do

1. **Check for sensitive files**: Warn about `.env`, `credentials.json`, or other secrets before staging
2. **Review changes**: Run `git status` and `git diff` to review all unstaged changes
3. **Stage changes**: Execute `git add -A` to stage all changes (or offer `git add -p` for partial)
4. **Review staged changes**: Run `git diff --cached` to review what will be committed
5. **Run pre-commit checks**: Run lint/typecheck if available in package.json
6. **Generate commit message**: Create a clear, conventional commit message following standard conventions
7. **Show preview & confirm**: Display the full commit and ask user to confirm/edit
8. **Commit changes**: Execute `git commit` with the generated message
9. **Check remote status**: Verify branch is up-to-date before pushing
10. **Push to remote**: Push the commit to the current branch (warn on main/master)

## When to use me

Use this when you want to:
- Commit all staged changes with a well-crafted commit message
- Ensure changes are properly reviewed before committing
- Quickly push commits to the remote repository

## How to use

1. Load this skill: `skill({ name: "git-commit-review" })`
2. I'll check for sensitive files and show you the changes
3. I'll offer staging options (all or partial)
4. I'll run lint/typecheck if available
5. I'll generate and show you the commit message for confirmation
6. You can edit the message if needed
7. I'll commit and push (or skip push if you prefer)

## Options

- **Skip push**: Tell me "don't push" to skip the push step
- **Amend**: Tell me "amend" to amend the last commit
- **Dry run**: Tell me "preview" to see what would happen without committing
- **Partial staging**: Tell me "partial" to interactively stage hunks

## Commit message format

I'll generate commit messages following conventional commits:
- `feat: add new feature X`
- `fix: resolve issue with Y`
- `refactor: simplify logic in Z`
- `docs: update documentation`
- `chore: update dependencies`

For multiple changes, I'll create a summary line and bullet points for details.

If the branch name contains an issue/ticket reference (e.g., `feature/ABC-123`), I'll include it in the commit message.

## Safety features

- **Sensitive file warnings**: Alert if `.env`, `credentials.json`, `*.key`, etc. are being staged
- **Hook verification**: Never skip pre-commit hooks (`--no-verify` is prohibited)
- **Branch protection**: Warn when pushing directly to `main` or `master`
- **Force push protection**: Use `--force-with-lease` instead of `--force` if force push is needed
- **Up-to-date check**: Warn if branch is behind remote before pushing
