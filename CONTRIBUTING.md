# Contributing to Cytroksys

This organization-level guide applies to every Cytroksys repository unless that repository provides its own `CONTRIBUTING.md`.

## Before You Start

- Search existing issues and PRs to avoid duplicates.
- Read the repository README and setup instructions.
- For security issues, follow `SECURITY.md` and do **not** open public issues.

## Development Workflow

1. Create a feature branch from `main` (`feat/<short-name>`, `fix/<short-name>`).
2. Use clear, conventional commit messages: `feat:`, `fix:`, `docs:`, `chore:`, `security:`, `refactor:`.
3. Keep pull requests small and focused on a single change.
4. Ensure tests and linters pass for the touched repository.
5. Request review from the code owners.

## Pull Requests

- Fill out the pull request template completely.
- Link related issues (`Closes #123`).
- Add or update tests for new or changed behavior.
- Update documentation and changelogs when relevant.

## Security

- Never commit secrets, tokens, keys, or credentials.
- Run secret scanning locally (for example, gitleaks) before pushing.
- Review new dependencies for known vulnerabilities before adding them.
- Report vulnerabilities privately per `SECURITY.md`.

## Code of Conduct

By participating in this project you agree to abide by `CODE_OF_CONDUCT.md`.
