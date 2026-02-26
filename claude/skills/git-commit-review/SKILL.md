---
name: commit
description: Review staged changes, create clear commit messages following conventional commits, and push to the current branch. Use when you want to commit changes with a well-crafted commit message.
disable-model-invocation: true
allowed-tools: Bash(git *), Read
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

## How to use

Invoke me directly with `/commit`:
- `/commit` - review, stage, commit and push all changes
- `/commit don't push` - commit without pushing
- `/commit amend` - amend the last commit
- `/commit partial` - interactively stage hunks

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
