---
name: commit
description: Write clear, accurate Git commit messages and create well-scoped commits. Use when committing changes or preparing commit messages, including Conventional Commit conventions and project-specific rules.
---

# Git Commit Messages

Create commit messages that explain the purpose of a change and keep history easy to scan and review.

## Before committing

1. Inspect repository state with `git status --short`.
2. Review staged and unstaged changes separately.
3. Confirm which files belong in the commit.
4. Check for secrets, generated files, accidental debug output, and unrelated edits.
5. Do not stage or commit files outside the user's intended scope.

## Message format

Use the repository's established convention. When no convention exists, use:

```text
type(scope): imperative summary

Explain why the change is needed and any important context.

Refs: #123
```

Common types:
- `feat`: add functionality.
- `fix`: correct incorrect behavior.
- `refactor`: restructure without changing behavior.
- `perf`: improve performance.
- `docs`: documentation-only change.
- `test`: add or update tests.
- `build`: build system or dependency changes.
- `ci`: automation and pipeline changes.
- `chore`: maintenance tasks.

## Subject rules

- Use imperative language.
- Describe the main outcome, not every implementation detail.
- Avoid trailing punctuation.
- Keep the subject concise, ideally within 50 to 72 characters.
- Add a scope only when it improves clarity.
- Follow any stricter repository-specific limit.

## Body and footer

Use the body to explain motivation, trade-offs, and relevant context. Wrap long lines sensibly. Add issue references only when they are real and supplied or verifiable. Use breaking-change footers when public compatibility changes.

## Sentry-specific repositories

When working in a Sentry repository, follow its current contribution and commit-message conventions. Do not assume a Sentry-specific type or issue format applies to unrelated repositories.

## Commit workflow

- Present the proposed commit message before committing when user approval is required.
- Commit only the reviewed staged diff.
- Verify the resulting commit with `git log -1 --oneline` and `git status --short`.
- Do not amend, force-push, or rewrite shared history without explicit instruction.

## Examples

```text
fix(auth): reject expired refresh tokens

Expired refresh tokens were accepted by one renewal path. Apply the
same expiry check used by the other authentication endpoints.
```

```text
docs: clarify local development setup
```
