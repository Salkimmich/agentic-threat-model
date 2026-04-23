# Contributing

Thanks for taking the time to contribute.

## Ways to contribute

- Tighten unclear guidance
- Add threat examples from production experience
- Improve templates so they are easier to use in real reviews
- Fix wording, structure, and broken links

## Pull request process

1. For larger changes, open an issue first so we can align on scope.
2. Keep PRs focused. Smaller PRs are easier to review and merge.
3. Explain what changed, why it changed, and what trade-offs you considered.
4. If you change guidance in one file, update related templates/examples too.

## Content standards

- Prefer concrete advice over abstract principles.
- Keep terms consistent across guides and templates.
- Call out vendor-specific guidance explicitly.
- Keep public documentation tool-neutral; do not include internal authoring tool references.

## Commit guidance

Use commit messages that explain intent, not just file edits.

## Local quality checks

Run local checks before opening a pull request:

1. Install pre-commit: `pip install pre-commit`
2. Install hooks: `pre-commit install`
3. Run all checks: `pre-commit run --all-files`

This runs markdown linting, markdown link checks, and basic hygiene checks.

## Issue triage labels

Use the triage guide in [`docs/issue-triage.md`](docs/issue-triage.md) for
priority, severity, and type label conventions.

## Security

Do not open public issues for sensitive vulnerabilities. Follow [`SECURITY.md`](SECURITY.md).
