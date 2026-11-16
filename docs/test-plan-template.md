# Test Plan

> Prioritise the demo path first. Do not aim for full coverage; aim for confidence that the P0 flow works every time.

## 1. Unit Testing

- Scope: pure logic, helpers, validators, data transformations.
- Tooling: _fill in once the stack is chosen_
- Owner: each developer for their own module.

| Module | What to test | Status |
|--------|--------------|--------|
|        |              |        |

## 2. API Testing

- Scope: every endpoint in `api-contracts-template.md`.
- For each endpoint verify: success response, validation errors, auth failures, not-found, response shape matches the contract.

| Endpoint | Success | Validation error | Auth error | Other | Status |
|----------|---------|------------------|------------|-------|--------|
|          |         |                  |            |       |        |

## 3. Integration Testing

- Scope: modules working together (frontend ↔ backend, backend ↔ database, backend ↔ AI/external service).
- Use real services where possible; use mocks only for flaky or paid external services.

| Integration | Scenario | Expected result | Status |
|-------------|----------|-----------------|--------|
|             |          |                 |        |

## 4. End-to-End Testing

- Scope: the full demo scenario from `problem-analysis-template.md`, run as a user would.
- Run it manually at every integration checkpoint, and again on the deployed environment before the demo.

| # | Step | Expected result | Pass/Fail |
|---|------|-----------------|-----------|
| 1 |      |                 |           |

## 5. Edge Cases

Check each that applies:

- [ ] Empty, missing or malformed input
- [ ] Very long or special-character input
- [ ] Unauthorised or expired session
- [ ] Duplicate submissions / double clicks
- [ ] External service slow, down or returning errors
- [ ] AI returns empty, invalid or unexpected output
- [ ] Large payloads / many items
- [ ] No data yet (empty state)
- [ ] Network interruption during a request
- [ ] Different browsers / screen sizes (if relevant)

## 6. Acceptance Criteria

The project is ready for demo when:

- [ ] All P0 requirements from the problem analysis pass end to end.
- [ ] All endpoints in the API contract behave as documented.
- [ ] No known critical bugs in the demo path.
- [ ] The app runs from a clean checkout using the README instructions.
- [ ] The deployed (or fallback local) environment has been tested within the last checkpoint.
- [ ] The demo scenario has been rehearsed at least once.
