# AGENTS.md — Guide for AI/LLM Coding Agents

Instructions for autonomous coding agents (Claude Code, Codex, Copilot, and similar) working in this repository.

## Project overview

WebMIDIBoard is a browser-based WebMIDI editor for the Kurzweil MIDIBoard.

**Current state: early development.** The repository contains open source infrastructure only — no application code yet. If a task seems to require app code that is not here, stop and ask the maintainer before scaffolding anything.

## Repository layout

| Path | Purpose |
| --- | --- |
| `README.md` | Project overview, browser support, entry point for newcomers. |
| `CONTRIBUTING.md` | Human contribution workflow: setup, PRs, commits, style. |
| `AGENTS.md` | This file: canonical guidance for AI/LLM agents. |
| `CLAUDE.md` | Pointer to this file for Claude Code (keep it a pointer only). |
| `CHANGELOG.md` | Keep a Changelog style log. Add user-visible changes under `[Unreleased]`. |
| `CODE_OF_CONDUCT.md` | Contributor Covenant v2.1 (do not modify). |
| `LICENSE` | Full GNU GPL v3 text (do not modify, do not "shorten"). See licensing rules below. |
| `SECURITY.md` | Vulnerability reporting policy. |
| `.github/ISSUE_TEMPLATE/` | Bug and feature request forms (YAML). |
| `.github/PULL_REQUEST_TEMPLATE.md` | Pull request template. |
| `.github/workflows/ci.yml` | CI: Markdown lint + workflow (actionlint) lint. |
| `.markdownlint.json` | markdownlint configuration used by CI and local checks. |

## Commands

| Task | Command |
| --- | --- |
| Lint all Markdown (must pass before committing) | `npx markdownlint-cli2 "**/*.md"` |
| Lint workflow files (if you touch `.github/workflows/`) | `actionlint` (installed via Homebrew: `brew install actionlint`; CI does this automatically) |

There are **no build, test, or run commands yet** because the application toolchain has not landed. When it does (see below), add its commands to this table and to `CONTRIBUTING.md` in the same change.

## Hard rules

1. **Never commit directly to `main`.** Always work on a branch and open (or prepare) a pull request.
2. **Do not modify `LICENSE`.** It is the full GNU GPL v3 text. This is a copyleft license: any application code added to this repository will be GPL v3. If a task implies mixing in non-GPL-compatible code or changing the license, stop and ask the maintainer.
3. **Do not scaffold application code or add dependencies** (package.json, framework, build tooling) unless the maintainer explicitly asks for it in the current task. If asked vaguely ("set up the project"), confirm the intended stack first; a reasonable default is modern TypeScript + Vite, but do not assume.
4. **Do not add third-party GitHub Actions or npm dependencies** without explicit maintainer approval; prefer the existing CI and official `actions/*` actions.
5. **Keep documentation in sync.** If you change the setup, workflow, or repository structure, update `README.md`, `CONTRIBUTING.md`, and this file together.
6. **Update the changelog** for user-visible behavior changes: add an entry under `[Unreleased]` in `CHANGELOG.md` (Keep a Changelog sections: Added, Changed, Fixed, ...).
7. **Use Conventional Commits** (`feat:`, `fix:`, `docs:`, `chore:`, ...) and small, focused commits.
8. **Keep Markdown lint-clean** (run the lint command before finishing) and use plain Markdown in PR descriptions — no raw angle-bracket tags.
9. **Do not commit secrets, credentials, or personal data.** Never add real device names or user info to tests, docs, or examples.

## Definition of done

- [ ] Change is minimal and focused on a single concern; diff is easy to review.
- [ ] `npx markdownlint-cli2 "**/*.md"` passes; workflow files pass actionlint if touched.
- [ ] `README.md` / `CONTRIBUTING.md` / this file updated if the setup or workflow changed.
- [ ] `CHANGELOG.md` `[Unreleased]` updated if the change is user-visible.
- [ ] Pull request opened against `main`, referencing related issues, with a short summary and how the change was tested.
