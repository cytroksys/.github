# GitHub Security Settings Checklist (Cytroksys)

Apply these settings at the **organization** and **repository** level to harden Cytroksys GitHub. Values marked *Recommended* reflect security best practices.

## Organization-level

- [ ] **Member privileges**
  - Base permissions for new members: *Read*.
  - Disable forking of private repositories by members unless required.
  - Require two-factor authentication for all organization members.
- [ ] **Repository creation**
  - Restrict repository creation to owners/admins.
  - Require sign-off on commits for web-based edits where feasible.
- [ ] **Security features (enable for all repos)**
  - Dependabot alerts and security updates.
  - Secret scanning and push protection.
  - Code scanning (CodeQL) default setup for eligible languages.
  - Dependency review on pull requests.
- [ ] **GitHub Actions**
  - Restrict Actions to GitHub-owned and explicitly allowed vendors.
  - Require approval for first-time contributors' workflow runs.
  - Default workflow permissions: *Read repository contents* (not read/write).
  - Disable Actions on forks unless needed.
- [ ] **Teams and access**
  - Use teams (`administrator`, `devops`) instead of direct user grants.
  - Grant least-privilege role per repo; audit quarterly.
- [ ] **Audit log**
  - Stream audit log to SIEM/log store; review periodically.
- [ ] **Private vulnerability reporting**
  - Enable for every public repository; use org-wide policy in `SECURITY.md`.

## Repository-level

- [ ] **Branch protection (main/default)**
  - Require a pull request before merging.
  - Require at least 1-2 approving reviews (dismiss stale reviews on new commits).
  - Require review from Code Owners.
  - Require status checks to pass (build, tests, security scans).
  - Require conversation resolution before merge.
  - Require signed commits.
  - Do not allow force pushes or deletions.
  - Require linear history (optional but recommended).
- [ ] **Environments**
  - Protect deployment environments with required reviewers and wait timers.
  - Restrict environment secrets to protected branches.
- [ ] **Secrets and variables**
  - Store secrets in environments; never in code.
  - Rotate on a defined schedule; revoke on offboarding.
  - Prefer OIDC over long-lived cloud credentials.
- [ ] **Dependabot**
  - Enable version updates via `.github/dependabot.yml`.
  - Auto-merge low-risk patch updates only after CI passes.
- [ ] **Code scanning**
  - Enable CodeQL default setup; triage and resolve alerts.
- [ ] **Secret scanning push protection**
  - Enabled; developers unblock only via documented process.
- [ ] **Release security**
  - Use signed tags/releases; generate SBOM/provenance (SLSA) for artifacts.

## Reusable Workflows

This repository provides reusable workflows under `.github/workflows/`:
- `reusable-security-scan.yml` - CodeQL + Gitleaks + Trivy for any caller repository.

Example caller:

~~~yaml
jobs:
  security:
    uses: cytroksys/.github/.github/workflows/reusable-security-scan.yml@main
    with:
      language: javascript-typescript
~~~

## Maintenance

- Review this checklist quarterly.
- Track changes as pull requests; keep an audit trail.
