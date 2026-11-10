# Agent instructions

Instructions for AI assistants and agents working in this repository. They must stay consistent with `CONTRIBUTING.md` and with the QA Manual in `docs/`.

## Project

HiperEats is a managed e-scooter fleet-as-a-service for food delivery from hypermarket food courts. See `README.md` for the concept.

- `backend/`: Spring Boot, Java 21, Maven
- `frontend/`: web UI in React
- `simulator/`: fleet telemetry simulator, own container, talks to the backend only through the telemetry integration interface

## Rules

- Follow `CONTRIBUTING.md` for code style, branch names and commit messages (story key `HE-<n>` first).
- Work on a feature branch and propose changes as a pull request. Never push to `main` and never merge.
- Keep business rules in the domain/service layer. Reach external systems only through their port and adapter.
- Write or update tests with every change: unit tests for business logic, integration tests for persistence, adapters and the REST API. Tag Gherkin scenarios with the business rule IDs they cover.
- Do not weaken or delete existing tests or quality gate settings to make a build pass.
- Never write secrets, credentials or real personal data. Use synthetic test data.
- State in the pull request description which parts were produced by an agent.

## Definition of done

See the definition of done in `CONTRIBUTING.md`.

## Build and test commands

_To be filled in when the walking skeleton is in place._
