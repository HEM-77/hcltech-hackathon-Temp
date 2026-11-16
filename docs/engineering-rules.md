# Engineering Rules

Short, practical rules for the whole team (and any AI agent). Prefer these over personal preference. If a rule blocks you, discuss it and record the change in `decisions.md`.

## 1. Coding Conventions

- Follow the idioms and the formatter/linter of the chosen language. Set one up on day one and run it before every commit.
- Keep functions small and single-purpose. Use clear, descriptive names.
- No dead code, commented-out blocks or leftover debug prints in PRs.
- Prefer simple solutions. Add abstractions only when something is used in at least two places.
- Comment the *why*, not the *what*.
- Add a dependency only if it clearly saves significant time; mention it in the PR.

## 2. Folder Structure Guidelines

- Organise by module/feature first, then by type, so each owner works in their own area.
- Keep one clear place for each of: source code, tests, configuration, docs.
- Shared code and contracts live in one agreed location owned by the integration owner.
- Do not commit generated files, build output, or local environment files.
- Document the final structure in the README once the stack is chosen.

## 3. Environment Variable Management

- All configuration and secrets come from environment variables, never hard-coded.
- Maintain a `.env.example` listing **every** variable with a placeholder value and a one-line description. It is committed.
- Real `.env` files are git-ignored and never shared in chat, issues or PRs.
- Use clear, consistent names (`UPPER_SNAKE_CASE`) and group them by service.
- Fail fast at startup with a clear message if a required variable is missing.
- If a secret is ever committed, rotate it immediately.

## 4. API Error Handling

- Follow the error shape defined in `api-contracts-template.md`.
- Use correct HTTP status codes: 400 validation, 401 unauthenticated, 403 forbidden, 404 not found, 500 unexpected.
- Never expose stack traces, internal paths or secrets to clients.
- Log the details server-side with enough context to debug.
- Handle failures of external services (timeouts, rate limits, bad responses) explicitly and return a useful error or fallback.
- The frontend must show a clear message on failure, never a blank screen.

## 5. Validation and Security Practices

- Validate all external input (request bodies, query params, uploaded files, AI output) at the boundary.
- Treat AI model output as untrusted input: validate its structure before using it.
- Use parameterised queries or the ORM; never build queries by string concatenation.
- Escape or sanitise anything rendered in the UI.
- Enforce authentication and authorisation on the server, not only in the UI.
- Never log secrets or personal data.
- Keep dependencies minimal and from trusted sources.
- Configure CORS narrowly rather than allowing all origins.

## 6. Git Commit Conventions

Use [Conventional Commits](https://www.conventionalcommits.org/):

```text
<type>(<optional scope>): <short imperative summary>
```

Types: `feat`, `fix`, `docs`, `refactor`, `test`, `chore`, `style`, `perf`.

Examples:
- `feat(auth): add login endpoint`
- `fix(api): return 400 on empty payload`

Rules:
- One logical change per commit; keep the summary under about 72 characters.
- Work on a `feature/*` branch and open a PR into `develop`. No direct pushes to `main` or `develop`. Only the release PR (`develop` → `main`) targets `main`.
- **PR titles:** feature PRs are squash-merged, so the PR title becomes the commit message in `develop`. It must follow the Conventional Commits format above, for example `feat(auth): add login endpoint`. Commits inside a feature branch should still be clear, but the PR title is what is kept.
- Never commit secrets, `.env` files or large generated files.

## 7. Rules for AI-Generated Code Review

AI-generated code is treated as a contribution from a new, unverified teammate.

- The author who prompted the code is fully responsible for it. "The AI wrote it" is not an excuse.
- Read and understand every line before committing. If you cannot explain it, do not submit it.
- Check that it matches the documented architecture and API contracts; reject invented endpoints, fields or env vars.
- Check for hallucinated libraries, functions or APIs. Verify that each dependency exists and is needed.
- Run it, and run or write tests. Do not trust code that has never been executed.
- Look for missing validation, unsafe handling of secrets, and swallowed errors.
- Look for over-engineering and unnecessary files; remove them.
- Make sure the AI did not overwrite or delete teammates' work.
- Mention in the PR when significant parts were AI-generated.
