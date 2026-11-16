# Claude Instructions

**Follow everything in [AGENTS.md](AGENTS.md).** This file adds Claude-specific expectations on top of it.

## Workflow

1. **Read first.** Read `README.md` and the relevant files in `docs/` before starting a task.
2. **Check existing code before modifying it.** Look at the files you will touch and their neighbours. Search for existing functions, patterns and conventions rather than writing duplicates.
3. **Plan before implementing.** For anything beyond a trivial edit, give a short plan first: what you will change, which files, and how you will verify it. Wait for the user's go-ahead on non-trivial or risky plans.
4. **Explain important architectural decisions.** When you choose between approaches (data model, library, structure, API shape), say what you chose, what the alternatives were and why. Propose an entry for `docs/decisions.md`.
5. **Verify.** Run relevant tests or the code itself, and report the actual results, including failures.

## Boundaries

- **Do not make commits or push changes without explicit approval** from the user. Never commit or push directly to `main` or `develop`.
- **Do not create branches without explicit approval.** You may suggest a branch name in the form `feature/<module>-<short-description>` (cut from `develop`).
- Do not merge, rebase or reset unless asked.
- Branching model and PR targets (feature PRs → `develop`, release PR `develop` → `main`) are described in `AGENTS.md` and `README.md`.
- Do not install packages, add dependencies, or change project configuration without saying so and getting approval.
- Do not invent APIs, environment variables or requirements. If it is not in the docs or the code, ask.
- Do not overwrite or delete existing files or work without approval.
- Keep changes minimal and focused on the request.

## Communication

- Be concise. Lead with the outcome, then the details that matter.
- Flag assumptions, open questions and risks explicitly.
