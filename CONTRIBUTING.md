# Contributing to WebMIDIBoard

Thank you for considering contributing! The project is in early development, so the process is intentionally light but clear.

## Ways to contribute

- **Report a bug** — use the [bug report template](.github/ISSUE_TEMPLATE/bug_report.yml) and include your browser, OS, and MIDI device setup.
- **Request a feature** — use the [feature request template](.github/ISSUE_TEMPLATE/feature_request.yml).
- **Open a pull request** — for fixes, small improvements, or documentation. See [Pull request process](#pull-request-process) below.
- **Help triage** — confirm or comment on existing issues, especially those labeled `good first issue`.

## Development setup

The application scaffold is not in the repository yet. Once it lands, this section will document:

- Runtime and toolchain requirements (for example, a specific Node.js version).
- Install, run, lint, and test commands.

Until then, documentation and repository infrastructure changes are the main way to contribute code. CI currently lints all Markdown and workflow files, so any docs change must keep those green:

```sh
npx markdownlint-cli2 "**/*.md"
```

If you are an AI/LLM coding agent, read [AGENTS.md](AGENTS.md) before making any changes.

## Pull request process

1. Fork the repository (if you do not have write access), then create a branch from `main`:
   - `fix/short-description` for bug fixes.
   - `feat/short-description` for features or other changes.
2. Make your changes in small, reviewable increments with clear commit messages (see [Commit conventions](#commit-conventions)).
3. Open a pull request against `main` using the [pull request template](.github/PULL_REQUEST_TEMPLATE.md) and reference related issues with `Closes #<number>`.
4. Respond to review feedback promptly, and keep the pull request focused on a single change where possible.

Do not push directly to `main`.

## Commit conventions

We follow [Conventional Commits](https://www.conventionalcommits.org/):

```text
<type>(<optional scope>): <short imperative summary>
```

Types in use: `feat`, `fix`, `docs`, `chore`, `refactor`, `test`, `ci`.

Examples:

```text
docs: update browser support notes in README
fix: ignore unhandled WebMIDI disconnect errors
ci: pin actionlint version in lint workflow
```

## Code and documentation style

- Follow the existing style of the files you touch. Project-wide tooling (formatter, linter) will be documented here once the application toolchain is chosen.
- Keep Markdown lint-clean: `npx markdownlint-cli2 "**/*.md"` (configuration lives in `.markdownlint.json`).
- Keep diffs minimal and easy to review.
- Update [README.md](README.md), this file, or [AGENTS.md](AGENTS.md) whenever the setup or workflow changes.
- Add user-visible behavior changes to the `[Unreleased]` section of [CHANGELOG.md](CHANGELOG.md).

## Security issues

Do not open public issues for security vulnerabilities. See [SECURITY.md](SECURITY.md).
