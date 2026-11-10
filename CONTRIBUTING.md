# Contributing to HiperEats

Short guidelines for every contributor, human or agent. The QA Manual (`docs/`) explains the rationale; keep both consistent with `AGENTS.md`.

## Workflow

We follow GitHub flow: `main` is always deployable and protected, and every change reaches it through a pull request.

1. Pick a story from the current sprint in Jira and move it to **In Progress**.
2. Create a branch named after the story key: `HE-<n>-short-description` (for example `HE-12-booking-endpoint`).
3. Start every commit message with the story key: `HE-12 add booking endpoint`.
4. Open a pull request whose title starts with the story key, fill in the template and move the story to **In Review**.
5. At least one other member approves; CI and the quality gate must pass. The author merges and moves the story to **Done**.

Agents never merge. A human approves every pull request.

## Code style

- **Java:** [Google Java Style Guide](https://google.github.io/styleguide/javaguide.html). Four-space indentation is accepted to match IDE defaults.
- Names in English. Classes are nouns, methods are verbs, tests describe behaviour (`bookingIsRefusedWhenBatteryBelowMinimum`).
- Business rules live in the domain/service layer, never in controllers or adapters.
- External systems (telemetry simulator, payment gateway) are reached only through a port interface and its adapter.
- No secrets in the repository. Configuration comes from environment variables or GitHub Secrets.
- **Frontend (React):** _style guide to define._

## Tests

- Unit tests for business logic; integration tests (Testcontainers, adapters, REST API) run separately from unit tests.
- Acceptance criteria of core stories are Gherkin scenarios automated with Cucumber, tagged with the business rule they cover (for example `@BR1`).
- Tests are linked to their Jira story so that Xray reports coverage.

## Definition of done (draft)

A story is done when:

- its acceptance criteria are met and automated;
- the required unit and integration tests are written and pass;
- CI is green and the SonarCloud quality gate passes on new code;
- the pull request was approved by another member;
- the Product Owner accepted the increment.

## Review checklist

- [ ] The pull request title and branch carry the story key.
- [ ] The change does what the story's acceptance criteria ask, and nothing unrelated.
- [ ] Business rules are tested, including boundary values.
- [ ] No business logic in controllers or adapters.
- [ ] No secrets, credentials or personal data.
- [ ] Names and structure are readable without extra explanation.
- [ ] AI review findings were considered, and the accepted or rejected ones are noted in the pull request.
