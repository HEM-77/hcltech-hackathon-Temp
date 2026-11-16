# Instructions for AI Coding Agents

These rules apply to any AI coding agent working in this repository. Human-readable context is in [README.md](README.md).

## Before You Write Code

1. **Read the project documentation first.** At minimum: `README.md` and everything relevant in `docs/` (problem analysis, architecture, API contracts, implementation plan, engineering rules, decisions).
2. **Understand the existing architecture** and the surrounding code before changing anything. Search for existing helpers and patterns and reuse them.
3. If requirements, contracts or ownership are unclear, **ask** instead of guessing.

## While Working

- Follow `docs/engineering-rules.md` (conventions, error handling, validation, security, commits).
- Make the smallest change that solves the task. Stay within the scope you were given.
- **Avoid unnecessary dependencies and over-engineering.** Prefer the standard library and what is already in the project.
- **Never invent** APIs, endpoints, environment variables, library functions or project requirements. If something is not documented or visible in the code, say so and ask.
- Do not hard-code secrets. When adding an environment variable, add it to `.env.example` and tell the user.
- If you change an API contract or make an architectural decision, update the relevant doc in `docs/` and `docs/decisions.md`.
- **Do not overwrite or delete existing work** without explicit approval. This includes other developers' modules, docs and uncommitted changes.

## Project Commands

> **Not yet populated.** These must be filled in by the team (the integration owner) after the actual problem statement is received and the technology stack is finalized and recorded in `docs/decisions.md`. Until then, do not guess or invent commands.

| Task | Command |
|------|---------|
| Install | `TBD` |
| Development | `TBD` |
| Build | `TBD` |
| Test | `TBD` |
| Lint | `TBD` |

## Before Reporting Completion

- **Run the relevant tests** (and linters/type-checks if configured). If there are none, run the code or the feature manually.
- Report honestly: what you changed, what you ran, and the results. State clearly anything that failed, was skipped, or is unverified.
- Do not claim something works if you have not run it.

## Git

Branching model: `main` (stable, tested) ← `develop` (integration) ← `feature/*` (individual work). Details are in `README.md`.

- Work only on a `feature/*` branch. If you are not on one, stop and ask.
- Never push directly to `main` or `develop`.
- Feature PRs target `develop`. Only the release PR (`develop` → `main`) targets `main`, after integration testing.
- Do not create branches without explicit approval. You may suggest a name, for example `feature/<module>-<short-description>`.
- Do not commit, push, merge or rewrite history unless the user explicitly asks you to.
