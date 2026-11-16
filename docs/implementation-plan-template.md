# Implementation Plan

> Split the work among four developers. Fill this in after the architecture and API contracts are agreed.

## 1. Team and Module Ownership

Each module has exactly one owner. Typical split (adapt to the actual problem):

| Developer | Role | Module(s) owned | Responsibilities |
|-----------|------|-----------------|------------------|
| Dev 1 | Technical lead / integration owner | Shared contracts, integration, deployment | See section 5 |
| Dev 2 | _e.g. Frontend_ | | |
| Dev 3 | _e.g. Backend / data_ | | |
| Dev 4 | _e.g. AI / services_ | | |

Everyone also: reviews PRs, writes tests for their own module, and keeps docs current.

## 2. Module Breakdown

| Module | Owner | Description | Key deliverables | Definition of done |
|--------|-------|-------------|------------------|--------------------|
|        |       |             |                  |                    |

## 3. Dependencies Between Modules

| Module | Depends on | What it needs | Needed by (time) | Workaround until ready (mock/stub) |
|--------|------------|---------------|------------------|-------------------------------------|
|        |            |               |                  |                                     |

Rule: unblock each other with agreed mocks based on `api-contracts-template.md` so nobody waits.

## 4. Milestones and Integration Checkpoints

| # | Time | Milestone | Integration checkpoint (what must work together) | Owner |
|---|------|-----------|--------------------------------------------------|-------|
| M0 | T+__h | Problem analysis, architecture and contracts agreed | Docs reviewed by all | Lead |
| M1 | T+__h | Project skeleton running, each module has a "hello world" | Frontend ↔ backend call works | Lead |
| M2 | T+__h | Core P0 flow works with real or mocked AI | End-to-end happy path | Lead |
| M3 | T+__h | All P0 features integrated and tested | Full demo scenario | Lead |
| M4 | T+__h | **Feature freeze.** Bug fixes only | Deployed demo environment | Lead |
| M5 | T+__h | Demo rehearsed, submission prepared | Final run-through | All |

## 5. Technical Lead / Integration Owner Responsibilities

- Owns the architecture, API contracts and `decisions.md`; approves any contract change.
- Keeps `main` working and demo-ready; runs the integration at every checkpoint.
- Reviews PRs that touch shared code or contracts.
- Resolves cross-module disagreements quickly and records the outcome.
- Tracks progress against milestones and cuts scope early if behind.
- Owns setup, deployment and environment configuration (`.env.example`, secrets handling).
- Runs the feature freeze and the final demo checklist.

## 6. Risks and Mitigations

| Risk | Likelihood | Impact | Mitigation |
|------|------------|--------|------------|
|      |            |        |            |

## 7. Communication

- Sync cadence (e.g. 10-minute stand-up every 3 hours):
- Where blockers are raised:
- Who decides when the team disagrees: the integration owner.
