# Hackathon Engineering Workspace

A reusable, stack-agnostic workspace for a four-person hackathon team. It holds the process, document templates and engineering rules we reuse for every hackathon. It contains **no application code** and makes **no technology choices**. Those are decided once the problem statement is known.

## Purpose

- Get from "problem statement received" to "working demo" quickly and without confusion.
- Keep four developers aligned on scope, contracts and ownership.
- Give AI coding agents (see [AGENTS.md](AGENTS.md) and [CLAUDE.md](CLAUDE.md)) the context and guardrails they need.

## Repository Layout

```text
Prac/
├── docs/
│   ├── problem-analysis-template.md
│   ├── architecture-template.md
│   ├── api-contracts-template.md
│   ├── implementation-plan-template.md
│   ├── engineering-rules.md
│   ├── test-plan-template.md
│   └── decisions.md
├── .github/PULL_REQUEST_TEMPLATE.md
├── README.md
├── AGENTS.md
├── CLAUDE.md
└── .gitignore
```

## Hackathon Workflow

1. **Understand (timebox it up front).** Decide as a team how much of the total hackathon time to spend on understanding and planning. Keep it a small share, scaled to the event's length. Everyone reads the problem statement. Fill in `docs/problem-analysis-template.md` together. Agree on scope and a minimal demo.
2. **Design.** Fill in `docs/architecture-template.md` and `docs/api-contracts-template.md`. Record every significant choice in `docs/decisions.md`.
3. **Plan.** Fill in `docs/implementation-plan-template.md`. Assign module owners and set integration checkpoints.
4. **Build.** Each developer works on their own module on a `feature/*` branch cut from `develop` and follows `docs/engineering-rules.md`.
5. **Integrate early and often.** Feature PRs are merged into `develop`. The integration owner tests the integrated result at each checkpoint and keeps `develop` working. `main` only receives tested releases from `develop`.
6. **Test.** Follow `docs/test-plan-template.md`. Prioritise the demo path.
7. **Freeze and demo.** Stop adding features at the agreed freeze time. Only fix bugs, using the same `feature/*` → `develop` path. After integration testing, open the release PR from `develop` to `main`, then rehearse the demo from `main`.

### Working with the templates

Each hackathon starts from its own fresh copy of this repository (see [Setup for a New Project](#setup-for-a-new-project)). **Fill the templates in place in `docs/`.** Do not copy them elsewhere. The `-template` suffix stays in the filenames so paths referenced from other documents remain valid. Delete sections that don't apply and keep the docs short and current. `docs/decisions.md` works the same way: keep the ADR template at the top and add real decisions below it.

## Git Branching and Pull Request Strategy

### Branches

| Branch | Purpose |
|--------|---------|
| `main` | Stable, tested version. Always demo-ready. |
| `develop` | Integration branch where finished features come together. |
| `feature/*` | Individual developer branches, cut from `develop`. |

- **Never push directly to `main` or `develop`.** All changes arrive through pull requests.
- Name feature branches `feature/<module>-<short-description>`, for example `feature/auth-login`. Bug fixes use the same pattern.
- Keep feature branches short-lived (hours, not days) and merge `develop` into them often.

### Pull requests

- **Feature PRs** (`feature/*` → `develop`): use `.github/PULL_REQUEST_TEMPLATE.md`. Squash-merge, then delete the branch.
- **Release PR** (`develop` → `main`): open it only after integration testing passes on `develop`. Use a regular merge commit (not squash) so `develop` and `main` do not diverge.
- Every PR needs at least one reviewer who is not the author. The integration owner reviews anything that touches shared contracts and approves release PRs.
- Review AI-generated code with the same rigour as human code (see `docs/engineering-rules.md`).
- PR titles follow Conventional Commits, because the title becomes the commit message on squash-merge (see `docs/engineering-rules.md`).
- AI agents may suggest branch names but must not create branches without explicit approval (see `AGENTS.md` and `CLAUDE.md`).

## Setup for a New Project

1. Create a new repository for the hackathon from a fresh copy of this workspace.
2. Confirm the default branch is `main`, then create `develop` from `main`.
3. Complete the planning docs in `docs/` before writing code.
4. Choose the stack and record it in `docs/decisions.md`.
5. Add the project's install, run and test commands to this README under a new **Project Setup** section.
6. Create a `.env.example` listing every required environment variable (names only, never real values). Copy it to `.env` locally. `.env` is git-ignored.
7. Enable branch protection on `main` and `develop` if the hosting platform allows it (require a PR and one review, no direct pushes).
8. Fill in the **Project Commands** section of `AGENTS.md` once the stack is final.
